<script>
    import PrevNext from '$lib/components/PrevNext.svelte';
</script>
<svelte:head>
    <title>2D Ball Bounce Eval | Suanna Zhong</title>
</svelte:head>

<div class="content_images">
    <div class="video-container">
        <video preload = "none" autoplay muted playsinline loop>
        <source
            src="https://de1wwae7728z6.cloudfront.net/videos/ballbounce/perfect-opus-sonnet-comparison.mp4"
            muted playsinline loop style="width: 100%; height: 100%;"
            type="video/mp4"
        />
        </video>
    </div>
</div>

<div class="blog-layout">
    <h1>2D Ball Bounce Eval</h1>

    <h3>
        Motion, LLM Evaluation <br>
        Timeline: __
        <br />
        <a target="_blank" href="https://github.com/suanna0/ball-graph-editor-eval">↗ GitHub</a>
    </h3>

    <div class = "gallery_content">
        <p>
            This eval compares how well different AI models animate a ball bounce by
            inspecting keyframes and bezier curves in a reconstructed graph instead of
            only grading the visual output.
        </p>
        <img
        loading="lazy" decoding="async"
        alt="Ball Path Drawing"
        src="https://de1wwae7728z6.cloudfront.net/images/ballbounce/animation-plan.png"
        />
    </div>

    <h2>Background</h2>
    <div class = "gallery_content">
        <p>
            AI-generated motion graphics are gaining a lot of popularity on platforms
            like Twitter, but they often lack the tasteful look that a human expert
            can achieve. There has been a surge of startups trying to create
            AI-assisted motion graphics editors, where an agent collaborates with
            the user to create motion graphics. These companies claim that unlike
            one-shot video generators, their agents create fully editable projects
            where the user can modify timing, keyframes, and curves in the graph
            editor.
        </p>
        <div class="content_images">
            <div class="video-container">
            <video preload = "none" autoplay muted playsinline loop>
                <source
                src="https://de1wwae7728z6.cloudfront.net/videos/ballbounce/ai-editors.mp4"
                muted playsinline loop style="width: 100%; height: 100%;"
                type="video/mp4"
                />
            </video>
            </div>
        </div>
        <p>
            Despite the rapid progress with every new model release, frontier models are not yet good collaborators for motion design.
            Today, AI-assisted video editing is at a state where it can copy a reference video at a mediocre level, but to polish the result to professional quality, users have to guess, wait, and check to see if they can tease out the right parameters. While this workflow initially seems faster, the process of 'debugging' can easily eclipse the supposed saved time.
        <br><br>
            For the agent to be an effective collaborator, the user should trust 
            that it not only has a working understanding of animation fundamentals such 
            as arcs, exaggeration, secondary action, etc., but can also produce deterministic results when given the same prompt. 
            If basic animation fundamentals are understood and common 
            operations can be done reliably in one shot, users will have more 
            trust that the agent will perform in a way that saves time without 
            sacrificing control and creativity.
        </p>
    </div>

    <h2>Why ball bounces?</h2>
    <p>
        A ball bounce is a beginner animation exercise that teaches students how 
        to use arcs, timing and spacing, and squash and stretch to simplify how 
        objects move in the real world. Unlike a physics simulation, curves are 
        flexible and can be manipulated to make motion realistic or exaggerated. 
        A skilled animator can make a form 
        read like a heavy bowling ball, a floaty beach ball, or a bouncing snowman 
        with extra airtime for dramatic effect. 
    </p>
    <div class="content_images">
        <div class="video-container">
        <video preload = "none" autoplay muted playsinline loop>
            <source
            src="https://de1wwae7728z6.cloudfront.net/videos/ballbounce/olaf.mp4"
            muted playsinline loop style="width: 100%; height: 100%;"
            type="video/mp4"
            />
        </video>
        </div>
    </div>
    <h2>Setup</h2>
    <p>
        Each rollout gives the model a task outlining the viewport size, ball's
        start and end position, animation duration, and which framework (CSS,
        GSAP, Lottie) to use. The model is instructed to create a ball bounce 
        animation with keyframes and easing only, without using a physics 
        simulation. The model has access to tools <code>read_file/write_file/list_dir/bash/finish</code>
        and can check their work by calling <code>render_graph</code>, which shows
        a graph plot of their work and a filmstrip. At grading time, a framework-specific
        adapter normalizes the model's work so that CSS, GSAP, and Lottie animations
        can be scored against the same rubric. 
    </p>
    <h2>Rubric</h2>
    <p>
        Each rubric item is graded pass/fail. Items are worth either 8 or 
        5 points to calculate a score out of 50. 
    </p>
    <p>
        1. At a given contact point, the ball's path does not bulge past its handlebars (8 pts)
    </p>
    <div class = "content_images">
        <img
            loading="lazy" decoding="async"
            alt="Rubric 1"
            src="https://de1wwae7728z6.cloudfront.net/images/ballbounce/rubric_1.png"
            style="max-width: 100%; height: auto;"
        />
    </div>
    <p>
        2. Contact points have broken tangents and apexes are smooth (8 pts)
    </p>
    <div class = "content_images">
        <img
            loading="lazy" decoding="async"
            alt="Rubric 2"
            src="https://de1wwae7728z6.cloudfront.net/images/ballbounce/rubric_2.png"
            style="max-width: 100%; height: auto;"
        />
    </div>
    <p>
        3. Translate X is linear or subtle ease-out (monotonic, non-increasing velocity) (8 pts)
    </p>
    <div class = "content_images">
        <img
            loading="lazy" decoding="async"
            alt="Rubric 3"
            src="https://de1wwae7728z6.cloudfront.net/images/ballbounce/rubric_3.png"
            style="max-width: 100%; height: auto;"
        />
    </div>
    <p>
        4. Every Y key is either a contact or apex, no unnecessary keys (8 pts)
    </p>
    <div class = "content_images">
        <img
            loading="lazy" decoding="async"
            alt="Rubric 4"
            src="https://de1wwae7728z6.cloudfront.net/images/ballbounce/rubric_4.png"
            style="max-width: 100%; height: auto;"
        />
    </div>
    <p>
        5. No stray keys on unused channels (scale/rotation) (8 pts)
    </p>
    <p>
        6. X and Y finish at the same frame (5 pts)
    </p>
    <p>
        7. The time of each bounce decreases at a constant rate (5 pts) 
    </p>
    <div class = "content_images">
        <img
            loading="lazy" decoding="async"
            alt="Rubric 7"
            src="https://de1wwae7728z6.cloudfront.net/images/ballbounce/rubric_7.png"
            style="max-width: 100%; height: auto;"
        />
    </div>
    <p>
        The rubric items are adapted from this <a target="_blank" href="https://vimeo.com/423284703?fl=pl&fe=vl">tutorial</a> created by Moshe Mahler.
    </p>
    <h2>Results</h2>
    <h2>Next Steps</h2>
     <p>
        The vanilla ball bounce exercise is effective because it is easy to spot when 
        the animation looks wrong and there are few enough moving parts that 
        the exercise stays focused on understanding the graph editor. Its 
        simplicity lends itself well to be extended towards more complex
        tasks. Some ideas of future evals include:
    </p> 
    <ul class="bulleted-list">
        <li>Animating different ball typies, such as a ping pong ball, bowling ball, or beach ball</li>
        <li>Model is given a scene where they fix or restyle an existing ball bounce</li>
        <li>A ball obstacle course with a single ball, multiple identical balls, heavy/light balls, etc.</li>
        <li>Attempting any of what's listed above in a 3D scene in three.js</li>
    </ul>
    <p>
        Online discourse treats the problem of creating beautiful things as an 
        impossible task, but like many other fields that AI has been capable of
        learning, successful motion is made up of small components that can be verified. Given
        the ephemeral nature of design trends, it's really interesting to think
        about what the lowest common denominators that have persisted throughout
        design history are, and speculate whether or not they will hold in the future. 
    <br><br>
        Automating motion design is just one example of how AI is changing what 
        it will mean to work as a designer. The creative world is headed 
        in a direction where it will be difficult for us to go back to a time 
        without artificial intelligence, but we can steer progress so that it 
        does not just benefit a small group of people.
    </p>
    <PrevNext />
</div>

<style>
    .blog-layout {
        max-width: 700px;
        margin: 0 auto;
    }

    .blog-layout :global(.gallery_content) {
        grid-template-columns: 1fr;
        gap: 1.25rem;
    }

    .blog-layout :global(.gallery_content img) {
        width: 100%;
    }

    .blog-layout :global(p) {
        max-width: 100%;
        line-height: 1.7;
    }

    @media only screen and (max-width: 850px) {
        .blog-layout {
            max-width: 100%;
        }
    }
</style>
