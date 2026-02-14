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
						entry.target.classList.add('fade-in');
						observer.unobserve(entry.target);
					}
				});
			},
			{ threshold: 0.1 }
		);

		document.querySelectorAll('img, video, .project_tag').forEach((el) => {
			if (!el.classList.contains('fade-in')) {
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