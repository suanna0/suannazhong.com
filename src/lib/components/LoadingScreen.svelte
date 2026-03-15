<script lang="ts">
	import { onMount } from 'svelte';
	import gsap from 'gsap';
	import { landingReady } from '$lib/stores';

	let overlay: HTMLDivElement;
	let track: HTMLDivElement;
	let fill: HTMLDivElement;

	onMount(() => {
		let visited = false;
		try { visited = !!sessionStorage.getItem('visited'); } catch {}

		if (visited) {
			overlay.style.display = 'none';
			landingReady.set(true);
			return;
		}

		try { sessionStorage.setItem('visited', 'true'); } catch {}

		// Indeterminate fill: crawl to 80% while assets load
		gsap.to(fill, { width: '80%', duration: 1.5, ease: 'power1.out' });

		const minDelay = new Promise((res) => setTimeout(res, 600));
		const loaded = new Promise((res) => {
			if (document.readyState === 'complete') res(null);
			else window.addEventListener('load', res, { once: true });
		});

		Promise.all([minDelay, loaded]).then(() => {
			gsap.killTweensOf(fill);

			const tl = gsap.timeline({
				onComplete: () => {
					overlay.style.display = 'none';
					landingReady.set(true);
				}
			});

			tl.to(fill, { width: '100%', duration: 0.2, ease: 'power2.out' })
			  .to(track, { opacity: 0, duration: 0.3, ease: 'power2.inOut' })
			  .to(overlay, { opacity: 0, duration: 0.5, ease: 'power2.inOut', delay: 0.3 });
		});
	});
</script>

<div bind:this={overlay} class="loading-overlay">
	<div bind:this={track} class="bar-track">
		<div bind:this={fill} class="bar-fill"></div>
	</div>
</div>

<style>
	.loading-overlay {
		position: fixed;
		inset: 0;
		background-color: var(--color-bg);
		z-index: 9999;
		pointer-events: none;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.bar-track {
		width: 200px;
		height: 4px;
		border-radius: 999px;
		background-color: color-mix(in srgb, var(--color-accent) 25%, transparent);
		overflow: hidden;
	}

	.bar-fill {
		height: 100%;
		width: 0%;
		border-radius: 999px;
		background-color: var(--color-accent);
	}
</style>
