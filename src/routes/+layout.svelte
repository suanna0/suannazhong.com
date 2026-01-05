<script lang="ts">
	import Nav from '../../src/lib/components/Nav.svelte';
	import favicon from '$lib/assets/favicon.svg';
	import '../app.css';
	import { page } from '$app/stores';
	import Footer from '$lib/components/Footer.svelte';
	export const prerender = true;
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<main>
  <Nav />
  <slot />
  <Footer />
</main>