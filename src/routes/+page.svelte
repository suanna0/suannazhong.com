<script>
    import Landing from '$lib/components/Landing.svelte';

    const projects = [
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
        {
            href: 'https://github.com/suanna0/ceci-capstone',
            type: 'video',
             src: 'https://de1wwae7728z6.cloudfront.net/videos/ceci-capstone/hero.mp4',
             alt: 'Motion Picture Soundtrack',
             tags: ['Google MediaPipe', 'OSC', 'WebSockets', 'TouchDesigner' ]
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
            tags: ['Fashion Photography']
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
            alt: '2025 Demo Reel',
            tags: ['Film', 'Animation', 'Reel']
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
                                <img src={project.src} alt={project.alt} />
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
                            <img src={project.src} alt={project.alt} />
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
