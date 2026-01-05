<svelte:head>
    <title>About | Suanna Zhong</title>
</svelte:head>

<section>
    <h1>About</h1>
    <div class="about_columns">
        <div>
            <p>
                Thanks for visiting my website! 
                <br><br>
                I am a fourth-year student in the Bachelor of Computer 
                Science and Arts (BCSA) program at Carnegie Mellon University, 
                studying Computer Science and Art. Being in this unique position 
                between disciplines, I enjoy being in 
                conversation with artists, researchers, engineers, and anyone who 
                feels like they fall somewhere in between. 
                <br><br>
                When I'm not working, you can probably find me making 
                <a href="https://art.suannazhong.com">art</a>, 
                listening to jazz, cafe hopping, or knitting winter clothes. 
                <br><br>
                suannaz [at] andrew [dot] cmu [dot] edu
                <br />
                <a target="_blank" href="https://www.linkedin.com/in/suannaz/"
                >LinkedIn</a
                > <br />
                <a target = "_blank" href = "https://drive.google.com/file/d/1Udtj4srKF6PpWqOm95pO_b8GuTY5bNHm/view?usp=sharing">
                Resume
                </a> <br />
                <a target = "_blank" href = "https://github.com/suanna0">
                Github
                </a>
                <br />
                <a target = "_blank" href = "https://www.instagram.com/suannazhong/">
                Instagram
                </a>
            </p>
            <div class = "clients_columns">
                <div>
                    <h2>Selected Clients:</h2>
                    <p>
                        Adolescent Content<br>
                        BonBonBardot!<br>
                        Common Sense Media<br>
                        Dehancer<br>
                        Marcus Rahauser<br>
                        Meta<br>
                        Pinterest<br>
                        VSCO<br /><br />
                    </p>
                </div>
                <div>
                    <h2>Music Clients:</h2>
                    <p>
                        Capitol Records<br>
                        Frankie Grande<br>
                        Jeremy Zucker<br>
                        JYP Entertainment<br>
                        Kali Uchis<br>
                        Kid Cudi<br>
                        Lang Lang<br>
                        Republic Records<br>
                        Stray Kids<br>
                        Virgin Music Group<br>
                        Etc.
                        <br /><br />
                    </p>
                </div>
            </div>
        </div>
        <div class = "image-container">
            <div class = "image-box">   
                <img loading="lazy" src="https://de1wwae7728z6.cloudfront.net/images/about/headshot.jpg" alt="headshot" />
            </div>
        </div>
    </div>
</section>

<style>
    .about_columns, .clients_columns {
        display: grid;
        grid-template-columns: 1fr 1fr;
        column-gap: 100px;
    }

    .image-container {
        position: relative;
        width: 80%;
        aspect-ratio: 4 / 3; 
    }

    .image-box {
        position: absolute;
        inset: 0;
        overflow: hidden;
    }

    .image-box img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        display: block;
    }
    
    @media only screen and (max-width: 850px) {
        .about_columns {
            grid-template-columns: 1fr;
        }

        .image-container {
        width: 100%;
        position: relative;
        }
    }

</style>