<script>
    import PrevNext from '$lib/components/PrevNext.svelte';
</script>
<svelte:head>
    <title>Motion Picture Soundtrack | Suanna Zhong</title>
</svelte:head>
<iframe src="https://www.youtube.com/embed/EKIO8SaApN4?si=mCcAfivma4WaZeVl" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
<h1>Motion Picture Soundtrack</h1>
<h3>
    p5.js, MIT ML5 Bodypose Keypoints library, 2023
</h3>
<p>
    Project for Fall 2023 CMU 60212, Creative Coding, taught by Professor Golan Levin.<br><br>
    Realtime animation that reacts to dancer's body movements tracked on a webcam via 2023 MIT ML5 Bodypose Keypoints library, performed by Ceci Sun.<br>
    <a target = "_blank" href = "https://github.com/suanna0/dev-lab/blob/main/motion_picture_soundtrack/motion_picture_soundtrack.js">Code</a>
</p>

<PrevNext
prev={{ href: '/reel', label: 'Previous' }}
next={{ href: '/malloc', label: 'Next' }}
/>