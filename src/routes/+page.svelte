<script>
    import Landing from '$lib/components/Landing.svelte';
    import { projects } from '$lib/projects.js';
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
                                <img loading="lazy" decoding="async" src={project.src} alt={project.alt} />
                            </div>
                        {/if}
                        <h3>{project.title}</h3>
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
                            <img loading="lazy" decoding="async" src={project.src} alt={project.alt} />
                        </div>
                    {/if}
                    <span class="lock-icon">🔒</span>
                    <h3>{project.title}</h3>
                {/if}
            </div>
        {/each}
    </div>
</section>
