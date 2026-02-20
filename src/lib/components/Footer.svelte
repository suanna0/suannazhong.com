<script lang="ts">
    export const title = "Footer";
    function backToTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      });
    }
</script>
  
<footer>    
    <p>SvelteKit · TypeScript · Vite</p>
    <button class="button" on:click={backToTop}>
        Back to Top ↑
    </button>
</footer>

  
<style>
    footer {
        padding-top: 20px;
        display: flex;
        max-width: 1500px;
        margin: 0 auto;
    }

    footer p:first-child {
        margin-right: auto;
    }

    footer button {
        background-color: transparent;
    }
</style>