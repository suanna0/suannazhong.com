<script>
    import Landing from '$lib/components/Landing.svelte';

    const projects = [
        {
            href: '/malloc',
            type: 'video',
            src: 'https://de1wwae7728z6.cloudfront.net/videos/malloc/hero.mp4',
            tags: ['CS Education', 'Front-end Dev']
        },
        {
            href: '/umusic',
            type: 'video',
            src: 'https://de1wwae7728z6.cloudfront.net/videos/umusic/hero.mp4',
            tags: ['Motion', 'Compositing', 'Color Grading']
        },
        {
            href: '/klee',
            type: 'video',
            src: 'https://de1wwae7728z6.cloudfront.net/videos/klee/16x9_promo.mp4',
            tags: ['Front-end Dev', 'Director/DP', 'Editor']
        },
        {
            href: '/reel',
            type: 'image',
            src: 'https://de1wwae7728z6.cloudfront.net/images/other/reel.jpg',
            alt: '2025 Demo Reel',
            tags: ['Film', 'Animation', 'Reel']
        },
        {
            href: '/mikegrail',
            type: 'image',
            src: 'https://de1wwae7728z6.cloudfront.net/images/mike-grail/thumbnail.jpg',
            alt: 'Mike Grail',
            tags: ['Creative Direction', 'Front-end Dev']
        },
        {
            href: '/dehancer',
            type: 'video',
            src: 'https://de1wwae7728z6.cloudfront.net/videos/dehancer/hero.mp4',
            tags: ['Affiliate Program', 'Color Grading']
        }
        // {
        //     href: '/motionpicture',
        //     type: 'image',
        //     src: 'https://de1wwae7728z6.cloudfront.net/images/tech/motion_picture_soundtrack.gif',
        //     alt: 'Motion Picture Soundtrack',
        //     tags: ['Real-time animation', 'Creative Code']
        // }
    ];
</script>

<svelte:head>
    <title>Work | Suanna Zhong</title>
</svelte:head>

<Landing />
<section class = "work" id = "mainSite">
    <h2>
        Selected Work:
    </h2>
    <div class="gallery_content">
        {#each projects as project}
            <div class="gallery">
                <a href={project.href}>
                    {#if project.type === 'video'}
                        <div class="video-container">
                            <video preload="none" autoplay muted playsinline loop>
                                <source src={project.src} type="video/mp4" />
                            </video>
                        </div>
                    {:else}
                        <div>
                            <img
                                src={project.src}
                                alt={project.alt}
                            />
                        </div>
                    {/if}
                    <div class="project_tag_container">
                        {#each project.tags as tag}
                            <span class="project_tag">{tag}</span>
                        {/each}
                    </div>
                </a>
            </div>
        {/each}
    </div>
</section>
