<script lang="ts">
	import { onMount } from 'svelte';
	import gsap from 'gsap';
	import { landingReady } from '$lib/stores';

	let overlay: HTMLDivElement;
	let fill: HTMLDivElement;

	onMount(() => {
		if (sessionStorage.getItem('visited')) {
			overlay.style.display = 'none';
			landingReady.set(true);
			return;
		}
		sessionStorage.setItem('visited', 'true');

		// Animate fill to 80% slowly while waiting for assets
		gsap.to(fill, {
			width: '80%',
			duration: 1.5,
			ease: 'power1.out'
		});

		const minDelay = new Promise((res) => setTimeout(res, 600));
		const loaded = new Promise((res) => {
			if (document.readyState === 'complete') res(null);
			else window.addEventListener('load', res, { once: true });
		});

		Promise.all([minDelay, loaded]).then(() => {
			// Fill to 100%, then fade out
			gsap.to(fill, {
				width: '100%',
				duration: 0.2,
				ease: 'power2.out',
				overwrite: true,
				onComplete: () => {
					gsap.to(fill.parentElement, {
						opacity: 0,
						duration: 0.3,
						ease: 'power2.inOut',
						onComplete: () => {
							gsap.to(overlay, {
								opacity: 0,
								delay: 0.3,
								duration: 0.5,
								ease: 'power2.inOut',
								onComplete: () => {
							overlay.style.display = 'none';
							landingReady.set(true);
						}
							});
						}
					});
				}
			});
		});
	});
</script>

<div bind:this={overlay} class="loading-overlay">
	<div class="bar-track">
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
