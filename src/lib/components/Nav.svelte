<script lang="ts">
    import { page } from '$app/stores';
    import { goto } from '$app/navigation';
  
    const navItems = [
      { label: 'Suanna Zhong', path: '/' },
      { label: 'Work', path: '/#mainSite' },
      { label: 'About', path: '/about' }
    ];
  
    function navigate(path: string) {
      goto(path);
    }
  </script>
  <nav>
    {#each navItems as item}
      <button
        class:active={$page.url.pathname === item.path}
        on:click={() => navigate(item.path)}
      >
        {item.label}
      </button>
    {/each}
  </nav>
  
  <style>
    nav {
      position: sticky;
      top: 0;
      z-index: 1000; 
  
      max-width: 1500px;
      margin: 0 auto;
      display: flex;
      background-color: var(--color-3);
      padding: 5px 0;
    }
  
    nav button {
      padding-left: 20px;
    }
  
    nav button:first-child {
      margin-right: auto;
      padding-left: 0;
    }
  </style>
  