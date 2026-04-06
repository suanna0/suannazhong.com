<script>
    let currentIndex = 0;
    
    const carouselItems = [
        {
            src: "https://de1wwae7728z6.cloudfront.net/images/about/suanna.jpg",
            alt: "headshot",
            description: "me!"
        },
        {
            src: "https://de1wwae7728z6.cloudfront.net/images/about/carousel/1.jpg",
            alt: "Oil paintings",
            description: "oil paintings"
        },
        {
            src: "https://de1wwae7728z6.cloudfront.net/images/about/carousel/2.jpg",
            alt: "Socks",
            description: "hand-knit ribbed socks"
        },
        {
            src: "https://de1wwae7728z6.cloudfront.net/images/about/carousel/3.jpg",
            alt: "Film Photography",
            description: "film photography"
        }
    ];
    
    function nextImage() {
        currentIndex = (currentIndex + 1) % carouselItems.length;
    }
    
    function prevImage() {
        currentIndex = (currentIndex - 1 + carouselItems.length) % carouselItems.length;
    }
</script>

<svelte:head>
    <title>About | Suanna Zhong</title>
</svelte:head>

<section>
    <h1>About</h1>
    <div class="about_columns">
        <div>
            <p>
                Hi there! I'm Suanna (pronounced Sue-Anne-Nuh), a fourth-year 
                student in the Bachelor of Computer Science and Arts (BCSA) 
                program at Carnegie Mellon University, where I study Computer 
                Science and Art. 
                <br><br>
                Whether it's solving an abstract math problem, composing an image, or designing a data structure, I really enjoy thinking of elegant solutions to interesting problems. Parallel and Sequential Data Structures and Algorithms, one of my favorite classes I've taken at CMU, has taught me to reach for Occam's razor: when multiple solutions exist, I go for the one with the fewest assumptions and the simplest explanation. 
                <br><br>
                When I'm not working, you can probably find me making
                <a target="_blank" href="https://art.suannazhong.com/pages/work.html">artwork</a>,
                listening to jazz, cafe hopping, or knitting winter clothes.
                <br><br>
                <a target="_blank" href="https://www.linkedin.com/in/suannaz/"
                >LinkedIn</a
                > · 
                <a target = "_blank" href = "https://github.com/suanna0">
                Github
                </a> · 
                <a target = "_blank" href = "https://www.instagram.com/suannazhong/">
                Instagram
                </a>
                <br />
                suannaz [at] andrew [dot] cmu [dot] edu
            </p>
            <h2>Selected Clients:</h2>
            <p>Adolescent Content, Akira Uchida, aron!, BonBonBardot!, Capitol Records, Chxrry, Common Sense Media, DAY6, Dehancer, Frankie Grande, Haiden Henderson, Jeremy Zucker, Jillian Jacqueline, JYP Entertainment, Kali Uchis, Kid Cudi, Lang Lang, Marcus Rahauser, Meta, Pinterest, Republic Records, Stray Kids, Virgin Music Group, VSCO, & more</p>
        </div>
        <div class = "image-container">
            <div class = "carousel-wrapper">
                {#if carouselItems.length > 1}
                    <button class="carousel-btn prev-btn" on:click={prevImage} aria-label="Previous image">‹</button>
                {/if}
                <div class = "image-box">   
                    <img loading="lazy" src={carouselItems[currentIndex].src} alt={carouselItems[currentIndex].alt} />
                </div>
                {#if carouselItems.length > 1}
                    <button class="carousel-btn next-btn" on:click={nextImage} aria-label="Next image">›</button>
                {/if}
            </div>
            {#if carouselItems[currentIndex].description}
                <div class="carousel-description">
                    {carouselItems[currentIndex].description}
                </div>
            {/if}
        </div>
    </div>
</section>

<style>
    .about_columns {
        display: grid;
        grid-template-columns: 1fr 1fr;
        column-gap: 30px;
    }

    .image-container {
        position: relative;
        max-width: 500px;
        aspect-ratio: 4 / 3;
        margin: 0 auto;
    }

    .carousel-wrapper {
        display: flex;
        align-items: center;
        gap: 10px;
        width: 100%;
        height: 100%;
    }

    .image-box {
        flex: 1;
        width: 100%;
        height: 100%;
        overflow: hidden;
    }

    .image-box img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        display: block;
    }

    .carousel-btn {
        color: var(--color-code);
        border: none;
        width: 40px;
        height: 40px;
        border-radius: 50%;
        cursor: pointer;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-shrink: 0;
        transition: background 0.3s ease;
    }

    .carousel-btn:hover {
        color: var(--color-accent);
    }

    .carousel-description {
        text-align: center;
        margin-top: 10px;
    }
    
    @media only screen and (max-width: 850px) {
        .about_columns {
            grid-template-columns: 1fr;
        }

        .image-container {
            width: 90%;
            aspect-ratio: 4 / 3;
            margin: 0 auto;
        }

        .carousel-description {
            font-size: 10px;
        }
    }

</style>