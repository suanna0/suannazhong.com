<script>
    import PrevNext from '$lib/components/PrevNext.svelte';
    import { fade } from 'svelte/transition';

    const images = [
        { alt: "BonBonBardot!", src: "https://de1wwae7728z6.cloudfront.net/images/commercial/00.jpg" },
        { alt: "BonBonBardot!", src: "https://de1wwae7728z6.cloudfront.net/images/commercial/01.jpg" },
        { alt: "Lucy (2024)", src: "https://de1wwae7728z6.cloudfront.net/images/commercial/02.jpg" },
        { alt: "Lucy (2025)", src: "https://de1wwae7728z6.cloudfront.net/images/commercial/03.jpg" },
        { alt: "Basil Racuk", src: "https://de1wwae7728z6.cloudfront.net/images/commercial/rishi.jpg" },
        { alt: "Basil Racuk", src: "https://de1wwae7728z6.cloudfront.net/images/commercial/07.jpg" },
        { alt: "Mike Grail", src: "https://de1wwae7728z6.cloudfront.net/images/commercial/04.jpg" },
        { alt: "Mike Grail", src: "https://de1wwae7728z6.cloudfront.net/images/commercial/05.jpg" },
        { alt: "Bryan and Cliff", src: "https://de1wwae7728z6.cloudfront.net/images/commercial/06.jpg" },
        { alt: "Luke", src: "https://de1wwae7728z6.cloudfront.net/images/commercial/08.jpg" },
        { alt: "Bloom by Brooke Schwartz", src: "https://de1wwae7728z6.cloudfront.net/images/commercial/09.jpg" },
        { alt: "The Wedding by Nicole Siyao Huang", src: "https://de1wwae7728z6.cloudfront.net/images/commercial/10.jpg" }
    ];

    /** @type {number | null} */
    let selectedIndex = null;

    /** @param {number} i */
    function openLightbox(i) {
        selectedIndex = i;
    }

    function closeLightbox() {
        selectedIndex = null;
    }

    function showPrev() {
        if (selectedIndex === null) return;
        selectedIndex = (selectedIndex + images.length - 1) % images.length;
    }

    function showNext() {
        if (selectedIndex === null) return;
        selectedIndex = (selectedIndex + 1) % images.length;
    }

    /** @param {KeyboardEvent} e */
    function handleKeydown(e) {
        if (selectedIndex === null) return;
        if (e.key === 'Escape') closeLightbox();
        else if (e.key === 'ArrowLeft') showPrev();
        else if (e.key === 'ArrowRight') showNext();
    }

    $: if (typeof document !== 'undefined') {
        document.body.style.overflow = selectedIndex !== null ? 'hidden' : '';
    }
</script>

<svelte:head>
    <title>Photography | Suanna Zhong</title>
</svelte:head>

<svelte:window on:keydown={handleKeydown} />

<h1>Photography</h1>
<h3>
    2024-Present
</h3>

<div class="photo_grid">
    {#each images as image, i}
        <button type="button" class="photo_grid_item" on:click={() => openLightbox(i)} aria-label={`View ${image.alt} larger`}>
            <img
            loading={i < 3 ? "eager" : "lazy"}
            fetchpriority={i < 3 ? "high" : undefined}
            decoding="async"
            alt={image.alt}
            src={image.src}
            />
        </button>
    {/each}
</div>

<PrevNext />

{#if selectedIndex !== null}
    <!-- svelte-ignore a11y_click_events_have_key_events -->
    <!-- svelte-ignore a11y_no_static_element_interactions -->
    <div class="lightbox" role="dialog" aria-modal="true" aria-label="Photo viewer" tabindex="-1" on:click={closeLightbox} transition:fade={{ duration: 150 }}>
        <button class="lightbox_close" on:click|stopPropagation={closeLightbox} aria-label="Close">&times;</button>
        <button class="lightbox_nav lightbox_prev" on:click|stopPropagation={showPrev} aria-label="Previous image">&#8249;</button>
        <!-- svelte-ignore a11y_click_events_have_key_events -->
        <!-- svelte-ignore a11y_no_static_element_interactions -->
        <div class="lightbox_content" on:click|stopPropagation>
            <div class="lightbox_image_wrap">
                {#key selectedIndex}
                    <img
                    src={images[selectedIndex].src}
                    alt={images[selectedIndex].alt}
                    transition:fade={{ duration: 150 }}
                    />
                {/key}
            </div>
            <p class="lightbox_caption">{images[selectedIndex].alt}</p>
        </div>
        <button class="lightbox_nav lightbox_next" on:click|stopPropagation={showNext} aria-label="Next image">&#8250;</button>
    </div>
{/if}

<style>
    .photo_grid {
        columns: 3;
        column-gap: 10px;
        padding: 5px 0px;
    }

    .photo_grid_item {
        display: block;
        width: 100%;
        break-inside: avoid;
        margin-bottom: 10px;
        padding: 0;
        border: none;
        background: none;
        font: inherit;
        cursor: pointer;
    }

    .photo_grid_item img {
        width: 100%;
        height: auto;
        display: block;
    }

    @media only screen and (max-width: 850px) {
        .photo_grid {
            columns: 2;
            column-gap: 5px;
            padding: 2.5px 0px;
        }

        .photo_grid_item {
            margin-bottom: 5px;
        }
    }

    .lightbox {
        position: fixed;
        inset: 0;
        background: rgba(0, 0, 0, 0.92);
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 1000;
    }

    .lightbox_content {
        display: flex;
        flex-direction: column;
        align-items: center;
        max-width: 90vw;
        max-height: 90vh;
    }

    .lightbox_image_wrap {
        position: relative;
        width: 90vw;
        height: 85vh;
        max-width: 90vw;
        max-height: 85vh;
    }

    .lightbox_content img {
        position: absolute;
        inset: 0;
        margin: auto;
        max-width: 100%;
        max-height: 100%;
        width: auto;
        height: auto;
        object-fit: contain;
        display: block;
        opacity: 1 !important;
        transform: none !important;
    }

    .lightbox_caption {
        color: #fff;
        margin-top: 12px;
        text-align: center;
    }

    .lightbox_close {
        position: absolute;
        top: 20px;
        right: 30px;
        line-height: 1;
        color: #fff;
        background: none;
        border: none;
        cursor: pointer;
        z-index: 1001;
    }

    .lightbox_nav {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        line-height: 1;
        color: #fff;
        background: none;
        border: none;
        cursor: pointer;
        padding: 10px 20px;
        z-index: 1001;
    }

    .lightbox_prev {
        left: 10px;
    }

    .lightbox_next {
        right: 10px;
    }

    @media only screen and (max-width: 850px) {
        .lightbox_nav {
            padding: 8px 12px;
        }

        .lightbox_close {
            top: 10px;
            right: 15px;
        }
    }
</style>
