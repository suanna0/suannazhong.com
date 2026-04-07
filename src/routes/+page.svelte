<script>
    import Landing from '$lib/components/Landing.svelte';

    const projects = [
        {
            href: '/ccc',
            type: 'image',
            src: 'https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/hero.gif',
            alt: 'Ceci Capstone',
            tags: ['Machine Learning','Google MediaPipe', 'Three.js']
        },
        {
            href: '/mikegrail',
            type: 'image',
            src: 'https://de1wwae7728z6.cloudfront.net/images/mike-grail/thumbnail.jpg',
            alt: 'Mike Grail',
            tags: ['Full-stack', 'Fashion Photography']
        },
        {
            href: '/malloc',
            type: 'video',
            src: 'https://de1wwae7728z6.cloudfront.net/videos/malloc/hero.mp4',
            tags: ['Front-end', 'CS Education']
        },
        // {
        //     href: '/umusic',
        //     type: 'video',
        //     src: 'https://de1wwae7728z6.cloudfront.net/videos/umusic/hero.mp4',
        //     tags: ['Motion', 'Animation', 'Compositing', 'Color Grading']
        // },
        {
            href: '/photo',
            type: 'video',
            src: 'https://de1wwae7728z6.cloudfront.net/videos/landing/photography.mp4',
            tags: ['Photography']
        },
        {
            href: '/klee',
            type: 'video',
            src: 'https://de1wwae7728z6.cloudfront.net/videos/klee/16x9_promo.mp4',
            tags: ['Director/DP', 'Video Editing', 'Front-end']
        },
        {
            href: '/reel',
            type: 'image',
            src: 'https://de1wwae7728z6.cloudfront.net/images/other/reel.jpg',
            alt: '2026 Demo Reel',
            tags: ['Demo Reel']
        }
        
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
                {#if project.href}
                    <a href={project.href}>
                        {#if project.type === 'video'}
                            <div class="video-container">
                                <video preload="none" autoplay muted playsinline loop>
                                    <source src={project.src} type="video/mp4" />
                                </video>
                            </div>
                        {:else}
                            <div>
                                <img loading="lazy" src={project.src} alt={project.alt} />
                            </div>
                        {/if}
                        <div class="project_tag_container">
                            {#each project.tags as tag}
                                <span class="project_tag">{tag}</span>
                            {/each}
                        </div>
                    </a>
                {:else}
                    {#if project.type === 'video'}
                        <div class="video-container">
                            <video preload="none" autoplay muted playsinline loop>
                                <source src={project.src} type="video/mp4" />
                            </video>
                        </div>
                    {:else}
                        <div>
                            <img loading="lazy" src={project.src} alt={project.alt} />
                        </div>
                    {/if}
                    <span class="lock-icon">🔒</span>
                    <div class="project_tag_container">
                        {#each project.tags as tag}
                            <span class="project_tag">{tag}</span>
                        {/each}
                    </div>
                {/if}
            </div>
        {/each}
    </div>
</section>
