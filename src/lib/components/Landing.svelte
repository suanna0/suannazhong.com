<script lang="ts">
	import { onMount } from 'svelte';
	import gsap from 'gsap';

	let heading: HTMLHeadingElement;

	onMount(() => {
		gsap.from(heading.querySelectorAll('a'), {
        opacity: 0,
        y: 10,
        delay: 0.4,
        stagger: 0.1,
        duration: 0.6,
        ease: 'power2.out'
    });
		gsap.from(heading, {
			opacity: 0,
			y: 30,
			duration: 1.2,
			ease: 'power2.out'
		});
	});

   
</script>

<section>
	<h1 bind:this={heading}>
		Suanna Zhong works across coding and photo/video 
		production. She previously worked on 
		<a target="_blank" href="https://www.universalmusic.com/">Universal Music Group's</a> 
		º1824 Content Team. Her past clients include 
		<a target="_blank" href="https://www.meta.com/">Meta</a>,
		<a target="_blank" href="https://www.pinterest.com/">Pinterest</a>, and 
		<a target="_blank" href="https://www.kidcudi.com/">Kid Cudi</a>.
	</h1>
</section>

<style>
	section {
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100vh;
		padding: 0 12vw;
	}

	h1 {
		text-align: center;
	}

	@media only screen and (max-width: 850px) {
		section {
			padding: 0 5px;
		}
	}

</style>
