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
        src="https://de1wwae7728z6.cloudfront.net/images/commercial/00.jpg"
        />
    </div>
    <div class="side_by_side">
        <img
        loading="eager" fetchpriority="high" decoding="async"
        alt="Erika (Bonbon)"
        src="https://de1wwae7728z6.cloudfront.net/images/commercial/01.jpg"
        />
    </div>
</div>
<div class = "side_by_side_content">
    <div class="side_by_side">
        <img
        loading="lazy" decoding="async"
        alt="Lucy (Fallingwater)"
        src="https://de1wwae7728z6.cloudfront.net/images/commercial/02.jpg"
        />
    </div>
    <div class="side_by_side">
        <img
        loading="lazy" decoding="async"
        alt="Lucy (Fall 2025)"
        src="https://de1wwae7728z6.cloudfront.net/images/commercial/03.jpg"
        />
    </div>
</div>

<div class="content_images">
    <img loading="lazy" decoding="async"
    alt = "Michael"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/commercial/04.jpg">
</div>


<div class = "side_by_side_content">
    <div class="side_by_side">
        <img
        loading="lazy" decoding="async"
        alt="Luke"
        src="https://de1wwae7728z6.cloudfront.net/images/commercial/06.jpg"
        />
    </div>
    <div class="side_by_side">
        <img
        loading="lazy" decoding="async"
        alt="Bryan and Cliff"
        src="https://de1wwae7728z6.cloudfront.net/images/commercial/07.jpg"
        />
    </div>
</div>

<div class="content_images">
    <img loading="lazy" decoding="async"
    alt = "Michael"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/commercial/05.jpg">
</div>

<div class = "side_by_side_content">
    <div class="side_by_side">
        <img
        loading="lazy" decoding="async"
        alt="Wedding"
        src="https://de1wwae7728z6.cloudfront.net/images/commercial/08.jpg"
        />
    </div>
    <div class="side_by_side">
        <img
        loading="lazy" decoding="async"
        alt="Bloom"
        src="https://de1wwae7728z6.cloudfront.net/images/commercial/09.jpg"
        />
    </div>
</div>

<div class="content_images">
    <img loading="lazy" decoding="async"
    alt = "Wedding Polaroids"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/commercial/10.jpg">
    </div>

<PrevNext />