<script lang="ts">
	import Nav from '../../src/lib/components/Nav.svelte';
	import favicon from '$lib/assets/favicon.svg';
	import '../app.css';
	import { page } from '$app/stores';
	import Footer from '$lib/components/Footer.svelte';
	import { onMount } from 'svelte';
	import { afterNavigate } from '$app/navigation';
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

	onMount(() => {
		observeMedia();
	});

	afterNavigate(() => {
		setTimeout(observeMedia, 50);
	});
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<main>
  <Nav />
  <slot />
  <Footer />
</main>