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
    Creative Direction, Front-end Dev (p5.js, GSAP, Svelte, TypeScript, Vite)
</h3>
<div class="gallery_content">
    <div>
        <p>
            <a target="_blank" href="https://www.mike-grail.com"
              >mike-grail.com</a
            > was born out of the frustration of seeing overly decorated prose 
            that is used to describe otherwise, pretty meaningless products or 
            services. Michael Yang and I decided to create a
            website to see how far we could polish it to mimic resale 
            marketplace sites such as 
            <a target = "_blank" href = "https://goat.com">Grailed</a> or 
            <a target = "_blank" href = "https://grailed.com">GOAT</a>. 
            Michael's writing is honest, appreciative, and never flashy, defying 
            the "in-group vs. out-group" dynamic that is typically seen in the 
            online fashion space.
            <br /><br />
            In this collaborative project, I led the visual 
            identity, implemented the site, and photographed and edited all 
            accompanying assets.
        </p>
    </div>
    <video 
    src="https://de1wwae7728z6.cloudfront.net/videos/mike-grail/s2.mp4"
    autoplay muted playsinline loop style="width: 100%; height: auto;">
</video>
</div>
<div class="video-container">
    <video preload="none" autoplay muted playsinline loop>
        <source src="https://de1wwae7728z6.cloudfront.net/videos/mike-grail/typography_photo.mp4" type="video/mp4" />
    </video>
</div>

<h2>Mike Captcha</h2>
<p>
    After a few months, I felt that the website could benefit 
    from a little more interaction. I wanted to create an element that was intuitive
    and playful, yet not too distracting.
</p>
<div class="video-container">
    <video preload="none" autoplay muted playsinline loop>
        <source src="https://de1wwae7728z6.cloudfront.net/videos/mike-grail/mike_captcha.mp4" type="video/mp4" />
    </video>
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
<p>
    The glasses slider was heavily inspired by this security verification on 
    Shopee. I have seen my fair share of slider puzzles but I had never seen one 
    that rotated the puzzle element.
</p>

<div class = "side_by_side_content">
    <div class = "side_by_side">
    <video 
        src="https://de1wwae7728z6.cloudfront.net/videos/mike-grail/shopee.mp4"
        autoplay muted playsinline loop style="width: 100%; height: auto;">
    </video>
    </div>
    <div class = "side_by_side">
    <video 
        src="https://de1wwae7728z6.cloudfront.net/videos/mike-grail/draft.mp4"
        autoplay muted playsinline loop style="width: 100%; height: auto;">
    </video>
    </div>
</div>

<div class = "gallery_content">
    <p>
        One challenge I faced was that I wasn't sure how to make the UI for the 
        grid Captcha. I knew that I wanted to use a 4x4 square grid, but I wasn't 
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

<h2>Backend</h2>
<p>
    The p5.js code tracks duration, number of movements, and jitter, 
    then sends the data to the server to be verified.
</p>
<div class="video-container">
    <video preload="none" autoplay muted playsinline loop>
        <source src="https://de1wwae7728z6.cloudfront.net/videos/mike-grail/backend.mp4" type="video/mp4" />
    </video>
</div>
<br>
<div class="content_images">
    <img loading = "lazy"
    alt = "Backend"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/mike-grail/backend_diagram.png">
</div>

<h2>Closing Thoughts:</h2>
<p>
    It was really interesting to think 
    of a way to combine my interest in fashion with creative web in a way that 
    felt authentic to me. Also, integrating the Captcha was a good way to 
    practice concepts I learned in my computer science classes. Thank you to Michael Yang for sending me pictures of himself and his 
    grails, even at the most inconvenient times. Special thanks to Leslie Liu, 
    Ian Giles, and Christy Yu for giving me a lot of great feedback on how to 
    improve the UI as well!
</p>


<PrevNext
prev={{ href: '/reel', label: 'Previous' }}
next={{ href: '/malloc', label: 'Next' }}
/>