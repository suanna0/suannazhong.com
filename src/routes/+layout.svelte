<script lang="ts">
	import Nav from '../../src/lib/components/Nav.svelte';
	import '../app.css';
	import { page } from '$app/stores';
	import Footer from '$lib/components/Footer.svelte';
	export const prerender = true;
</script>

<main>
  <Nav />
  <slot />
  <Footer />
</main>