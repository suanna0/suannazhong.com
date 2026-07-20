<script lang="ts">
	import Nav from '../../src/lib/components/Nav.svelte';
	import favicon from '$lib/assets/favicon.svg';
	import '../app.css';
	import { page } from '$app/stores';
	import Footer from '$lib/components/Footer.svelte';
	import { onMount } from 'svelte';
	import { beforeNavigate, afterNavigate, goto } from '$app/navigation';
	import gsap from 'gsap';

	let transitionOverlay: HTMLDivElement;
	let navigating = false;
	let mediaObserver: IntersectionObserver | null = null;

	function observeMedia() {
		if (mediaObserver) mediaObserver.disconnect();

		const observer = new IntersectionObserver(
			(entries) => {
				entries.forEach((entry) => {
					if (entry.isIntersecting) {
						const el = entry.target as HTMLElement;
						if (el.tagName === 'IMG') {
							const img = el as HTMLImageElement;
							img.dataset.inView = 'true';
							if (img.complete) img.classList.add('fade-in');
						} else {
							el.classList.add('fade-in');
						}
						observer.unobserve(el);
					}
				});
			},
			{ threshold: 0.1 }
		);
		mediaObserver = observer;

		document.querySelectorAll('img, video, .gallery h3').forEach((el) => {
			if (!el.classList.contains('fade-in')) {
				if (el.tagName === 'IMG') {
					const img = el as HTMLImageElement;
					img.addEventListener('load', () => {
						if (img.dataset.inView === 'true') img.classList.add('fade-in');
					}, { once: true });
				}
				observer.observe(el);
			}
		});
	}

	onMount(() => {
		observeMedia();
	});

	beforeNavigate(({ to, cancel }) => {
		if (navigating || !to || !transitionOverlay) return;
		cancel();
		navigating = true;
		gsap.killTweensOf(transitionOverlay);
		gsap.fromTo(transitionOverlay,
			{ opacity: 0 },
			{
				opacity: 1,
				duration: 0.3,
				ease: 'power1.inOut',
				onComplete: () => { goto(to.url.pathname + to.url.hash); }
			}
		);
	});

	afterNavigate(() => {
		navigating = false;
		if (transitionOverlay) {
			gsap.killTweensOf(transitionOverlay);
			gsap.to(transitionOverlay, {
				opacity: 0,
				duration: 0.3,
				ease: 'power1.inOut',
			});
		}
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

<div bind:this={transitionOverlay} class="transition-overlay"></div>
<main>
  <Nav />
  <slot />
  <Footer />
</main>
