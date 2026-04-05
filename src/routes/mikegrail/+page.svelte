<script>
    import PrevNext from '$lib/components/PrevNext.svelte';
</script>
<svelte:head>
    <title>Mike Grail | Suanna Zhong</title>
</svelte:head>

<div class="content_images">
    <img loading = "lazy"
    alt = "Header"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/mike-grail/header.jpg">
</div>

<h1>Mike Grail</h1>
<h3>
    Creative Direction, Full-stack Dev (GSAP, p5.js, Svelte, TypeScript, Vite) 
    <br />
    <a target="_blank" href="https://www.mike-grail.com">↗ Live Site</a> · 
    <a target="_blank" href="https://github.com/suanna0/mike-grail">↗ GitHub</a> 
</h3>
<div class="gallery_content">
    <div>
        <p>
            Mike Grail is dedicated to showcasing Michael Yang's designer clothing collection.
            Michael's writing is honest, appreciative, and never flashy, defying 
            the "in-group vs. out-group" dynamic that is typically seen in the 
            online fashion space.
            <br /><br />
            Mike Captcha, an extension of the site,  is a fashion themed, 
            behavior-based CAPTCHA. It collects interaction metrics through 
            the browser, then validates behavior server-side through API calls, 
            and returns a pass token that gates access to the site's landing page.
            <br /><br />
            In this project, I led the visual 
            identity, photographed and edited all accompanying assets, and 
            implemented the site's frontend and backend functionality.
        </p>
    </div>
<video 
    src="https://de1wwae7728z6.cloudfront.net/videos/mike-grail/mike_captcha.mp4"
    autoplay muted playsinline loop style="width: 100%; height: auto;">
</video>
</div>

<div class="video-container">
    <video preload="none" autoplay muted playsinline loop>
        <source src="https://de1wwae7728z6.cloudfront.net/videos/mike-grail/typography_photo.mp4" type="video/mp4" />
    </video>
</div>

<h2>Server-side Validation</h2>
<p>
    The browser tracks duration, number of movements, and jitter, 
    then sends the data to the server to be verified.
</p>
<div class="content_images">
    <img loading = "lazy"
    alt = "Backend"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/mike-grail/backend_diagram.png">
</div>
<div class="video-container">
    <video preload="none" autoplay muted playsinline loop>
        <source src="https://de1wwae7728z6.cloudfront.net/videos/mike-grail/backend.mp4" type="video/mp4" />
    </video>
</div>
<br>

<h2>"Select all squares" Captcha</h2>
<div class = "gallery_content">
    <p>
        One challenge I faced was that I wasn't sure how to make the UI for the 
        grid captcha. I knew that I wanted to use a 4x4 square grid, but I wasn't 
        sure to what extent I should mimic Google's reCaptcha. Luckily, I was able
        to get feedback from multiple people who were more knowledgeable about 
        UI/UX design. Eventually, I arrived at a design that was more minimal and 
        cohesive with the rest of the website. 
    </p>
    <div class="video-container">
        <video preload="none" autoplay muted playsinline loop>
            <source src="https://de1wwae7728z6.cloudfront.net/videos/mike-grail/ui.mp4" type="video/mp4" />
        </video>
    </div>
</div>
<div class = "side_by_side_content">
    <div class = "side_by_side">
    <video 
        src="https://de1wwae7728z6.cloudfront.net/videos/mike-grail/captcha_kapital.mp4"
        autoplay muted playsinline loop style="width: 100%; height: auto;">
    </video>
    </div>
    <div class = "side_by_side">
        <video 
        src="https://de1wwae7728z6.cloudfront.net/videos/mike-grail/captcha_cdg.mp4"
        autoplay muted playsinline loop style="width: 100%; height: auto;">
    </video>
    </div>
</div>


<h2>Closing Thoughts</h2>
<div class="gallery_content">
    <p>
        It was really interesting to think 
        of a way to combine my interest in fashion with creative web in a way that 
        felt authentic to me. Also, integrating the Captcha was a good way to 
        practice concepts I learned in my computer science classes. Thank you to Michael Yang for sending me pictures of himself and his 
        grails, even at the most inconvenient times. Special thanks to Leslie Liu, 
        Ian Giles, and Christy Yu for giving me a lot of great feedback on how to 
        improve the UI as well!
    </p>
    <video 
        src="https://de1wwae7728z6.cloudfront.net/videos/mike-grail/s2.mp4"
        autoplay muted playsinline loop style="width: 100%; height: auto;">
    </video>

</div>

<div class="content_images">
    <img loading = "lazy"
    alt = "Footer"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/mike-grail/footer.jpg">
</div>


<PrevNext
prev={{ href: '/ccc', label: 'Previous' }}
next={{ href: '/malloc', label: 'Next' }}
/>