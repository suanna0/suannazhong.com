<head>
    <title>Malloc Visualizer | Suanna Zhong</title>
</head>
<video 
src="https://de1wwae7728z6.cloudfront.net/videos/malloc/malloc-demo.mp4"
autoplay muted playsinline loop style="width: 100%; height: auto;">
</video>
<h1>Malloc Visualizer</h1>
<h3>
    CS Education, Front-end Dev (Svelte, TypeScript, Vite)
</h3>
<div class="gallery_content">
<div>
    <p>
    <a 
    target = "_blank" 
    href = "https://malloclab.com/">malloclab.com</a
    >
    <br><br>
    CMU's <a 
    target = "_blank" 
    href = "https://www.cs.cmu.edu/~213/">15-213: Introduction to 
    Computer Systems</a
    > has played a major role in the way CS is taught today. The class 
    not only pioneered well-known labs such as 
    <code>bomblab</code> and <code>attacklab</code>, but their slide 
    have been used by computer systems courses at other universities, 
    setting a higher standard for modern CS education.
    <br><br>
    During the lab, I observed places where clearer visuals and fewer 
    words could help students grasp the key concepts more effectively. I 
    decided to create a website to explore this idea.
    </p>
</div>

<video 
    src="https://de1wwae7728z6.cloudfront.net/videos/malloc/final_shortened.mp4"
    autoplay muted playsinline loop style="width: 100%; height: auto;">
</video>
</div>
<div class="content_images">
<img loading = "lazy"
alt = "Malloc Typography"
    id="content_img"
    src="https://de1wwae7728z6.cloudfront.net/images/malloc/malloc_typography.png">
</div>

<div class="content_images">
<img loading = "lazy"
alt = "Malloc Colors"
    id="content_img"
    src="https://de1wwae7728z6.cloudfront.net/images/malloc/malloc_colors.png">
</div>

<div class="content_images">
<img loading = "lazy"
alt = "Malloc Site Structure"
    id="content_img"
    src="https://de1wwae7728z6.cloudfront.net/images/malloc/malloc_site_structure.png">
</div>


<div class="gallery_content">
<div>
    <p>
    The opening page is interactive, functioning as a black-box 
    representation of <code>malloc</code>. To keep the code clean, I 
    used a Model View Controller structure to separate mouse 
    interactions from drawing logic. 
    </p>
</div>

<div class="video-container">
    <video autoplay muted playsinline loop>
    <source
        src="https://de1wwae7728z6.cloudfront.net/videos/malloc/front_page.mp4"
                    type="video/mp4"
    />
    </video>
</div>
</div>

<p>
    Using Adobe After Effects, I created animations to illustrate specific 
    concepts.
</p>

<div class="side_by_side_content">
<div class="side_by_side">
    <div class="video-container">
    <video autoplay muted playsinline loop>
        <source
        src="https://de1wwae7728z6.cloudfront.net/videos/malloc/final_shortened.mp4"
                        type="video/mp4"
        />
    </video>
    </div>
</div>

<div class="side_by_side">
    <div class="video-container">
    <video autoplay muted playsinline loop>
        <source
        src="https://de1wwae7728z6.cloudfront.net/videos/malloc/implicit_margin.mp4"
                        type="video/mp4"
        />
    </video>
    </div>
</div>
</div>

<video 
src="https://de1wwae7728z6.cloudfront.net/videos/malloc/explicit_list.mp4"
autoplay muted playsinline loop style="width: 100%; height: auto;">
</video>

<!-- <h2>Visualizing two data structures:</h2>

<div class="side_by_side_content">
<div class="side_by_side">
    <img
    src="https://de1wwae7728z6.cloudfront.net/images/malloc/explicit_slide.jpg"
    />
</div>

<div class="side_by_side">
    <div class="video-container">
    <video autoplay muted playsinline loop>
        <source
        src="https://de1wwae7728z6.cloudfront.net/videos/malloc/implicit_0.mp4"
                        type="video/mp4"
        />
    </video>
    </div>
</div>
</div>

<p>
When I did the lab for the first time, I had a difficult time grasping the 
concept that heap and the explicit free list are two separate data 
structures, and that if the author chooses to implement LIFO insertion, 
the blocks in the free list may be out of address order. I wanted to 
clearly establish that concept when describing the difference between the 
implicit and explicit list. Hence, the explicit list has lines that point 
blocks in the heap to their corresponding location in the free list.
</p>

<h2>Takeaways:</h2>
<p>More pictures, less words. establishing consistency.</p> -->
