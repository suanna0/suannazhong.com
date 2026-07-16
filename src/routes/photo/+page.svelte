<script>
    import PrevNext from '$lib/components/PrevNext.svelte';
</script>

<svelte:head>
    <title>Photography | Suanna Zhong</title>
</svelte:head>

<h1>Photography</h1>
<h3>
    2024-Present
</h3>
<div class = "side_by_side_content">
    <div class="side_by_side">
        <img
        loading="eager" fetchpriority="high" decoding="async"
        alt="Lucy (Bonbon)"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/0.jpg"
        />
    </div>
    <div class="side_by_side">
        <img
        loading="eager" fetchpriority="high" decoding="async"
        alt="Erika (Bonbon)"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/1.jpg"
        />
    </div>
</div>
<div class = "side_by_side_content">
    <div class="side_by_side">
        <img
        loading="lazy" decoding="async"
        alt="Lucy (Fallingwater)"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/2.jpg"
        />
    </div>
    <div class="side_by_side">
        <img
        loading="lazy" decoding="async"
        alt="Lucy (Fall 2025)"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/3.jpg"
        />
    </div>
</div>

<div class="content_images">
    <img loading="lazy" decoding="async"
    alt = "Michael"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/4.jpeg">
</div>

<!-- <div class="content_images">
    <img loading = "lazy"
    alt = "Michael Closeup"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/55.jpg">
</div> -->

<div class = "side_by_side_content">
    <div class="side_by_side">
        <img
        loading="lazy" decoding="async"
        alt="Wedding"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/6.jpg"
        />
    </div>
    <div class="side_by_side">
        <img
        loading="lazy" decoding="async"
        alt="Bloom"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/7.jpg"
        />
    </div>
</div>

<div class="content_images">
    <img loading="lazy" decoding="async"
    alt = "Wedding Polaroids"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/8.jpg">
    </div>

<PrevNext />