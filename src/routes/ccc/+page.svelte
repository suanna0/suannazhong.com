<script>
    import PrevNext from '$lib/components/PrevNext.svelte';
</script>
<svelte:head>
    <title>Ceci Capstone GUI | Suanna Zhong</title>
</svelte:head>

<div class="video-container">
    <video preload="none" autoplay muted playsinline loop>
    <source src="https://de1wwae7728z6.cloudfront.net/videos/ceci-capstone/hero.mp4" type="video/mp4" />
    </video>
</div>

<h1>Ceci Capstone GUI</h1>
<h3>
    TouchDesigner, p5.js, ml5.js, Google MediaPipe, OSC, WebSockets, Node.js
    <br />
    <a target="_blank" href="https://github.com/suanna0/ceci-capstone">↗ GitHub</a> 
</h3>
<p>
    For Ceci Sun's senior thesis dance performance, I created a 
    GUI/debugging interface that sends OSC messages to TouchDesigner.
<!--             
    It would be a good idea to talk about TCM and being ABC and our 8
    year friendship.  -->
</p>
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

<div class="video-container">
    <video preload="none" autoplay muted playsinline loop>
        <source src="https://de1wwae7728z6.cloudfront.net/videos/ceci-capstone/0209.mp4" type="video/mp4" />
    </video>
</div>
<div class = "gallery_content">
    <p>
        MediaPipe is really powerful because it can retreive a lot of information 
        super quickly. The framework provided three parameters for all 33 joints and 
        deciding which ones to use so that the mapping would look intuitive
        to the audience was an interesting challenge. When connecting the data to TouchDesigner, I observed that the all of the data had 
        a natural jitter, so it turned out that only one to two parameters was enough to communicate 
        the overall movement of the choreography. 
        <br><br>
        I decided to use the distance between two fixed points to drive the animation. 
        For example, the distance between the left hand and the left shoulder is
        easy for the dancer to control. 
        The slider in the p5 GUI would control how sensitive the mapping was.     
    </p>
        <img
        alt="Slider"
        src="https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/slider.png"
        />
</div>
<h2>Inspiration</h2>
<p>daito manabe rhizomatiks, brian eno discreet music, etc. </p>
<div class="content_images">
    <img loading = "lazy"
    alt = "Inspiration"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/inspo.png">
</div>
<h2>🚧 Check back soon for more progress :)</h2>


<PrevNext
prev={{ href: '/malloc', label: 'Previous' }}
next={{ href: '/photo', label: 'Next' }}
/>