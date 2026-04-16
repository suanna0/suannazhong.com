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
        loading="lazy"
        alt="Lucy"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/0.jpg"
        />
    </div>
    <div class="side_by_side">
        <img
        loading="lazy"
        alt="Erika"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/1.jpg"
        />
    </div>
</div>
<div class = "side_by_side_content">
    <div class="side_by_side">
        <img
        loading="lazy"
        alt="Ceci"
        src="https://de1wwae7728z6.cloudfront.net/images/other/251230_ceci.jpg"
        />
    </div>
    <div class="side_by_side">
        <img
        loading="lazy"
        alt="Lucy"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/3.jpg"
        />
    </div>
</div>

<div class="content_images">
<img loading = "lazy"
alt = "Wedding"
    id="content_img"
    src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/4.jpg">
</div>

<div class = "side_by_side_content">
    <div class="side_by_side">
        <img
        loading="lazy"
        alt="Wedding"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/5.jpg"
        />
    </div>
    <div class="side_by_side">
        <img
        loading="lazy"
        alt="Bloom"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/6.jpg"
        />
    </div>
</div>

<div class="content_images">
    <img loading = "lazy"
    alt = "Wedding Polaroids"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/photo/commercial/7.jpg">
    </div>

<PrevNext
prev={{ href: '/malloc', label: 'Previous' }}
next={{ href: '/klee', label: 'Next' }}
/>