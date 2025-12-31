<script>
    import Landing from '$lib/components/Landing.svelte';
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
        <div class="gallery">
            <a href="/malloc">
            <div class="video-container">
                <video preload="none" autoplay muted playsinline loop>
                <source src="https://de1wwae7728z6.cloudfront.net/videos/malloc/hero.mp4" type="video/mp4" />
                </video>
            </div>
            <div class = "project_tag_container">
                <span class="project_tag">CS Education</span>
                <span class="project_tag">Front-end Dev</span>
            </div>
            </a>
        </div> 

        <div class="gallery">
            <a href="/umusic">
            <div class="video-container">
                <video preload="none" autoplay muted playsinline loop>
                <source src="https://de1wwae7728z6.cloudfront.net/videos/umusic/hero.mp4" type="video/mp4" />
                </video>
            </div>
            <div class = "project_tag_container">
                <span class="project_tag">Motion</span>
                <span class="project_tag">Compositing</span>
                <span class="project_tag">Color Grading</span>
            </div>
            </a>
        </div>

        <div class="gallery">
            <a href="/klee">
            <div class="video-container">
                <video preload="none" autoplay muted playsinline loop>
                <source src="https://de1wwae7728z6.cloudfront.net/videos/klee/16x9_promo.mp4" type="video/mp4" />
                </video>
            </div>
            <div class = "project_tag_container">
                <span class="project_tag">Front-end Dev</span>
                <span class="project_tag">Director/DP</span>
                <span class="project_tag">Editor</span>
            </div>
            </a>
        </div>

        <div class="gallery">
            <a href="/dehancer">
            <div class="video-container">
                <video preload="none" autoplay muted playsinline loop>
                <source src="https://de1wwae7728z6.cloudfront.net/videos/dehancer/hero.mp4" type="video/mp4" />
                </video>
            </div>
            <div class = "project_tag_container">
                <span class="project_tag">Affiliate Program</span>
                <span class="project_tag">Color Grading</span>
            </div>
            </a>
        </div> 

        <div class="gallery">
            <a href="/reel">
                <div>
                <img
                    src="https://de1wwae7728z6.cloudfront.net/images/other/reel.jpg"
                    alt="2025 Demo Reel"
                />
                <div class = "project_tag_container">
                    <span class="project_tag">Film</span>
                    <span class="project_tag">Animation</span>
                    <span class="project_tag">Reel</span>
                </div>
            </a>
        </div> 

        <div class="gallery">
            <a href="/motionpicture">
                <div>
                <img
                    src="https://de1wwae7728z6.cloudfront.net/images/tech/motion_picture_soundtrack.gif"
                    alt="Motion Picture Soundtrack"
                />
                <div class = "project_tag_container">
                    <span class="project_tag">Real-time animation</span>
                    <span class="project_tag">Creative Code</span>
                </div>
                </div>
            </a>
        </div>
</div>
</section>
