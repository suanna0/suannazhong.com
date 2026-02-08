<script>
    import PrevNext from '$lib/components/PrevNext.svelte';
</script>
<svelte:head>
    <title>Motion Picture Soundtrack | Suanna Zhong</title>
</svelte:head>
<h1>Motion Picture Soundtrack</h1>
<h3>
    TouchDesigner, p5.js, ml5.js, Google MediaPipe, OSC, WebSockets, Node.js
</h3>
<div class="gallery_content">
    <div>
        <p>
            Realtime animation for Ceci Sun's senior thesis performance.
            It would be a good idea to talk about TCM and being ABC and our 8
            year friendship. TouchDesigner 
            to create more complex animations that better utilized GPU computing power.
        </p>
    </div>
<video 
    src="https://de1wwae7728z6.cloudfront.net/videos/mike-grail/mike_captcha.mp4"
    autoplay muted playsinline loop style="width: 100%; height: auto;">
</video>
</div>
<h2>Background</h2>
<div class = "gallery_content">
<p>
    In Golan Levin's Fall 2023 Creative Coding course, I used p5.js to create a <a target="_blank" href="https://youtu.be/EKIO8SaApN4?si=ccBJpT4CoezVMuKn">
    gesture expander</a> that rendered in real-time. The project used the
    via the MIT ML5 Bodypose Keypoints library. Ceci Sun, a friend and
    dancer at Johns Hopkins University, performed choreography to one of my 
    favorite songs at the time, "Motion Picture Soundtrack" by Radiohead.
    <br /><br />
    When Ceci and I caught up in Winter 2025, she asked if I would be interested
    in creating a new version of the project for her senior thesis performance.
    Given that it had been two years since we last collaborated, and newer 
    technologies had become available, I was really excited to create an improved 
    version.  
</p>
<img 
alt = "2023 Performance"
src = "https://de1wwae7728z6.cloudfront.net/images/tech/motion_picture_soundtrack.gif"
/>
</div>
<h2>Web Render vs. OSC</h2>
<div class = "gallery_content">
    <p>
        I had two options for connecting MediaPipe to TouchDesigner. TouchDesigner's 
        Web Render node can display a webpage as a texture, which would show the 
        MediaPipe visualization directly. With this approach, I would receive an 
        image as an input. The alternative was using OSC to send the numerical pose 
        data. I decided to use OSC because it has a lower latency and the programming
        workflow of using variables as opposed to encoding and decoding an image 
        felt more intuive to me. Additionally, I could create effects using 
        placeholder values in TouchDesigner and then replace them with the OSC values later.
    </p>
        <img
        alt="Web Render"
        src="https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/webrender-osc.png"
        />
</div>
<h2>Inspiration</h2>
<p>reference daito manabe obviously but i want it to feel more organic less "look at the computer oooo ahhh "</p>
<div class="content_images">
    <img loading = "lazy"
    alt = "Malloc Typography"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/inspo.png">
</div>

<PrevNext
prev={{ href: '/reel', label: 'Previous' }}
next={{ href: '/malloc', label: 'Next' }}
/>