<script lang="ts">
	import { onMount } from 'svelte';
	import gsap from 'gsap';

	let overlay: HTMLDivElement;

	onMount(() => {
		// Skip loading screen if already visited this session
		if (sessionStorage.getItem('visited')) {
			overlay.style.display = 'none';
			return;
		}
		sessionStorage.setItem('visited', 'true');

		const hide = () => {
			gsap.to(overlay, {
				opacity: 0,
				duration: 0.6,
				ease: 'power2.inOut',
				onComplete: () => {
					overlay.style.display = 'none';
				}
			});
		};

		// Wait for all assets + a minimum delay so it doesn't flash
		const minDelay = new Promise((res) => setTimeout(res, 600));
		const loaded = new Promise((res) => {
			if (document.readyState === 'complete') res(null);
			else window.addEventListener('load', res, { once: true });
		});

		Promise.all([minDelay, loaded]).then(hide);
	});
</script>

<div bind:this={overlay} class="loading-overlay"></div>

<style>
	.loading-overlay {
		position: fixed;
		inset: 0;
		background-color: var(--color-bg);
		z-index: 9999;
		pointer-events: none;
	}
</style>
