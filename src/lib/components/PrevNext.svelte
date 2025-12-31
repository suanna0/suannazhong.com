<script lang="ts">
  export let prev: { href: string; label?: string } | null = null;
  export let next: { href: string; label?: string } | null = null;
</script>

<prevnext class="prev-next">
  {#if prev}
    <a class="prev" href={prev.href}>
      <p>
          &larr; {prev.label ?? 'Previous'}
      </p>
    </a>
  {/if}

  {#if next}
    <a class="next" href={next.href}>
      <p>
          {next.label ?? 'Next'} &rarr;
      </p>
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
