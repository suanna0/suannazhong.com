<script lang="ts">
	import Nav from '../../src/lib/components/Nav.svelte';
	import favicon from '$lib/assets/favicon.svg';
	import '../app.css';
	import { page } from '$app/stores';
	import Footer from '$lib/components/Footer.svelte';
	import { onMount } from 'svelte';
	import { beforeNavigate, afterNavigate, goto } from '$app/navigation';
	import LoadingScreen from '$lib/components/LoadingScreen.svelte';
	import gsap from 'gsap';
	export const prerender = true;

	function observeMedia() {
		const observer = new IntersectionObserver(
			(entries) => {
				entries.forEach((entry) => {
					if (entry.isIntersecting) {
						const el = entry.target as HTMLElement;
						// For images, wait until loaded before fading in
						if (el.tagName === 'IMG') {
							const img = el as HTMLImageElement;
							img.dataset.inView = 'true';
							if (img.complete) {
								img.classList.add('fade-in');
							}
						} else {
							el.classList.add('fade-in');
						}
						observer.unobserve(el);
					}
				});
			},
			{ threshold: 0.1 }
		);

		document.querySelectorAll('img, video, .project_tag').forEach((el) => {
			if (!el.classList.contains('fade-in')) {
				// Add load listener for images
				if (el.tagName === 'IMG') {
					const img = el as HTMLImageElement;
					img.addEventListener('load', () => {
						if (img.dataset.inView === 'true') {
							img.classList.add('fade-in');
						}
					}, { once: true });
				}
				observer.observe(el);
			}
		});
	}

	let transitionOverlay: HTMLDivElement;
	let navigating = false;

	onMount(() => {
		observeMedia();
	});

	beforeNavigate(({ to, cancel }) => {
		if (navigating || !to) return;
		cancel();
		navigating = true;
		gsap.to(transitionOverlay, {
			opacity: 1,
			duration: 0.3,
			ease: 'power2.inOut',
			onComplete: () => goto(to.url.pathname + to.url.hash)
		});
	});

	afterNavigate(() => {
		navigating = false;
		gsap.to(transitionOverlay, {
			opacity: 0,
			duration: 0.3,
			ease: 'power2.inOut'
		});
		setTimeout(observeMedia, 50);
	});
</script>

<style>
	.transition-overlay {
		position: fixed;
		inset: 0;
		background-color: var(--color-bg);
		z-index: 9998;
		opacity: 0;
		pointer-events: none;
	}
</style>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<LoadingScreen />
<div bind:this={transitionOverlay} class="transition-overlay"></div>
<main>
  <Nav />
  <slot />
  <Footer />
</main>