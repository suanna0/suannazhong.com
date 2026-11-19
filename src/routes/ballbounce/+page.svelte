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
            src="/tmp/perfect-opus-sonnet-comparison.mp4"
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
        alt="Slider"
        src="/tmp/animation-plan.png"
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
                src="/tmp/ai-editors.mp4"
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
            that it has a working understanding of animation fundamentals such 
            as arcs, exaggeration, secondary action, and other tools to create 
            appeal. If basic animation fundamentals are understood and common 
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
        By making adjustments in the graph editor, an animator can make a ball 
        read like a heavy bowling ball, a floaty beach ball, or a cartoon circle 
        with extra airtime for comedic effect. This exercise is effective 
        because it is easy to spot when the animation looks wrong, and there are 
        few enough moving parts that the exercise stays focused on reading the 
        graph editor.
    </p>
    <h2>Setup</h2>
    <p>
        brief, agent tools
    </p>
    <h2>Rubric</h2>
    <p>
    The rubric items are adapted from this <a target="_blank" href="https://vimeo.com/423284703?fl=pl&fe=vl">tutorial</a> created by Moshe Mahler.
1. At a given contact point, the ball's path does not bulge past its handlebars (8 pts)
2. Contact points have broken tangents and apexes are smooth (8 pts)
3. Translate X is linear or subtle ease-out (monotonic, non-increasing velocity) (8 pts)
4. Every Y key is either a contact or apex, no unnecessary keys (8 pts)
No stray keys on unused channels (scale/rotation) (8 pts)
X and Y finish at the same frame (5 pts)
The time of each bounce decreases at a constant rate (5 pts)
    </p>
    <h2>Results</h2>
    <h2>What's next</h2>
    <p>
        other things to test: next steps: material, build another environment to 
        teach the AI to fix the ball bounce or adhere to a style, ball obstacle 
        course, 3D test,
        <br><br>

        more broad ideas:
        more verifiable tests? creating some kind of syntax where we can apply 
        operations on top of, check if associativity matters and yields the 
        same output 
        <br><br>
        people complain about AI-generated visual slop a lot. motion is a hot 
        topic and people think taste can't be trained. some of that may be true 
        but to many people's suprrise, there is a lot of determinism and verifiability akin to other fields that AI is good at. 
        <br><br>
        The creative world is headed in a direction where we cannot go back to the state before Artificial Intelligence but we can steer it in a direction so that its not just benefiting a small group of people. full autonomy bad, effective collaborator good. 
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
