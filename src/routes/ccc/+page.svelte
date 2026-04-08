<script>
    import PrevNext from '$lib/components/PrevNext.svelte';
</script>
<svelte:head>
    <title>一 (yi) / oneness | Suanna Zhong</title>
</svelte:head>

<div class="content_images">
    <img loading = "lazy"
    alt = "Inspiration"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/evelyn_solo.gif">
</div>

<h1>一 (yi) / oneness</h1>
<h3>
    TouchDesigner, p5.js, ml5.js, Google MediaPipe, OSC, WebSockets, Node.js
    <br />
    <a target="_blank" href="https://github.com/suanna0/ceci-capstone">↗ GitHub</a> 
    <span class="locked-link" title="Coming Soon">↗ Full Performance</span>
</h3>
<p>
    For Ceci Sun's senior thesis, 一 (yi) / oneness, I was the sole designer of 
    the real-time visuals accompanying her live performance and a GUI/debugging 
    interface that sends OSC messages to TouchDesigner.
</p>

<div class="side_by_side_content">
    <div class="side_by_side">
      <img loading = "lazy"
      alt="Cong"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/rehearsal_1.gif">
    </div>

    <div class="side_by_side">
      <img loading = "lazy"
      alt="0311"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/rehearsal_2.gif">
    </div>
</div>

<div class="content_images">
    <img loading = "lazy"
    alt = "Inspiration"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/backdrop.gif">
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
    loading="lazy"
    alt = "2023 Performance"
    src = "https://de1wwae7728z6.cloudfront.net/images/tech/motion_picture_soundtrack.gif"
    />
</div>
<h2>Thematic Underpinnings</h2>
<p>
    Much of Ceci's creative practice is informed by mind-body connections 
    through qigong principles. Her work combines Eastern and Western 
    philosophical perspectives: Eastern traditions emphasize balance and the 
    flow of energy, while Western contemporary dance practices explore 
    emotional expression and psychological experience. As an American-born 
    Chinese American, I have also grown up with a mix of Eastern and Western 
    philosophies. Topics such as meditation and traditional Chinese medicine 
    are deeply ingrained in my personal life, which I was able to draw on when 
    working on this project.
</p>
<div class="content_images">
    <img loading = "lazy"
    alt = "Inspiration"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/phases.jpg">
</div>
<h2>Inspiration</h2>
<p>
    I was heavily inspired by <a target="_blank" href="https://youtu.be/s_S3fomiXO0?si=M4i9_uZZ90DdhHuP">discrete figures</a> by Daito Manabe's Rhizomatiks Research group,
    as well as Lingdong Huang's <a target="_blank" href="https://studioforcreativeinquiry.org/project/shan-shui">{'{'}Shan, Shui{'}'}*</a>,
    which Golan had previously shown us and undeniably influenced how we approached the mountain visuals.
    For time-based visuals, I often find it easier to figure out the music first, and
    Ceci sent me some placeholder tracks that helped guide what the visuals should look like.
</p>
<div class="content_images">
    <img loading = "lazy"
    alt = "Inspiration"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/inspo.png">
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
        <br><br>
        When it came to deciding what equipment to use for the live performance, 
        it turned out that using the OSC approach would be more reliable. This is
        because images are very expensive to send. Depending on the size of the 
        venue, using longer cables may introduce some undefined behavior as well. 
    </p>
        <img
        loading="lazy"
        alt="Web Render"
        src="https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/webrender-osc.png"
        />
</div>

<div class="video-container">
    <video preload="none" autoplay muted playsinline loop>
        <source src="https://de1wwae7728z6.cloudfront.net/videos/ceci-capstone/0209.mp4" type="video/mp4" />
    </video>
</div>
<br>
<div class="video-container">
    <video preload="none" autoplay muted playsinline loop>
    <source src="https://de1wwae7728z6.cloudfront.net/videos/ceci-capstone/hero.mp4" type="video/mp4" />
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
        loading="lazy"
        alt="Slider"
        src="https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/slider.png"
        />
</div>

<iframe src="https://www.youtube.com/embed/3_EyuqmPKQU?si=_IyEoh6HBfDE6UyS" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<h2>Limitations and Challenges</h2>
<p>
    Since I only needed a few parameters to communicate the movement, it was not 
    necessary to use all 33 joints. Unfortunately, the MediaPipe library does not 
    support turning off certain joints. If I were to scale up the project, I would
    need to create a custom model that only uses the necessary joints to improve
    overall performance. Also, MediaPipe is best trained for waist-up poses 
    filmed on the webcam and tracks at most one person at a time. When an improved
    model is created in the future, a lot of new possibilities will open up in 
    terms of the types of performances that can be created.
    <br><br>

        A challenging aspect of this project was actually making the generated 
        visuals tell a story. One piece of advice that Golan gave me that helped 
        a lot was to think of particles as a substance that can be molded to 
        mimic natural phenomena, such as clouds, snow, or sand. To me, it felt
        more intuitive to use p5.js to fine-tune the parameters 
        to get the desired effect.
</p>

<iframe src="https://www.youtube.com/embed/qUeFP3tmdD8?si=6pdXUnSuTTpM-XCO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


<h2>More Experiments</h2>

<iframe src="https://www.youtube.com/embed/LXtQTE9_FiI?si=jAqJRG_MCIye9gZV" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<iframe src="https://www.youtube.com/embed/lHTtWkZlEdk?si=_lToTBQnA9ICkkTc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<div class="side_by_side_content">
    <div class="side_by_side">
      <img loading = "lazy"
      alt="Flyer"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/4x5-flyer.png">
    </div>

    <div class="side_by_side">
      <img loading = "lazy"
      alt="4x5 Flyer"
        id="content_img"
        src="https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/flyer.gif">
    </div>
</div>

<h2>Credits</h2>

<div class="credits">
    <div class = "role">
        Director
    </div>
    <div class = "name">
        Ceci Sun
    </div>
</div>

<div class="credits">
    <div class = "role">
        Choreographer
    </div>
    <div class = "name">
        Ceci Sun
    </div>
</div>

<div class="credits">
    <div class = "role">
        Performers
    </div>
    <div class = "name">
        Ceci Sun, Evelyn Au, Amari James, Parris Hester
    </div>
</div>

<div class="credits">
    <div class = "role">
        Lighting Designer
    </div>
    <div class = "name">
        Calder Sprinkle
    </div>
</div>

<div class="credits">
    <div class = "role">
        Interactive Motion Designer
    </div>
    <div class = "name">
        Suanna Zhong
    </div>
</div>

<div class="credits">
    <div class = "role">
        Videographer
    </div>
    <div class = "name">
        Andrew Van Allen
    </div>
</div>

<div class="credits">
    <div class = "role">
        Pittsburgh Dancer
    </div>
    <div class = "name">
        Viviana Chen
    </div>
</div>

<h2>Special Thanks</h2>
<div class = "gallery_content">
    <p>
        I would like to thank Ceci Sun for inviting me to collaborate on this project,
        Golan Levin and Kyle McDonald for their mentorship, Calder Sprinkle for 
        programming the lighting to go with the projections, and Viviana Chen for 
        testing out the software in Pittsburgh. I would also like to thank my 
        beautiful and intelligent classmates for believing in me and providing candid 
        feedback to help me grow. 
    </p>
    <img
    loading="lazy"
    alt = "Suanna and Ceci"
    src = "https://de1wwae7728z6.cloudfront.net/images/ceci-capstone/suanna_ceci.jpg"
    />
</div>

<PrevNext
prev={{ href: '/reel', label: 'Previous' }}
next={{ href: '/mikegrail', label: 'Next' }}
/>

<style>
    .locked-link {
        color: var(--color-accent);
        opacity: 0.4;
        cursor: not-allowed;
    }
</style>