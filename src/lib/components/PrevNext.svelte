<script>
  import { page } from '$app/stores';
  import { projects } from '$lib/projects.js';

  $: index = projects.findIndex(p => p.href === $page.url.pathname);
  $: prev = index > 0 ? { href: projects[index - 1].href } : { href: projects[projects.length - 1].href };
  $: next = index < projects.length - 1 ? { href: projects[index + 1].href } : { href: projects[0].href };
</script>

<prevnext class="prev-next">
  {#if prev}
    <a class="prev" href={prev.href}>
      <p>&larr; Previous</p>
    </a>
  {/if}

  {#if next}
    <a class="next" href={next.href}>
      <p>Next &rarr;</p>
    </a>
  {/if}
</prevnext>

<style>
  .prev-next {
    display: flex;
    justify-content: space-between;
    margin-top: 4rem;
  }
</style>
