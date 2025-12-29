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
  
  <nav class="nav">
    {#each navItems as item}
      <button
        class:active={$page.url.pathname === item.path}
        on:click={() => navigate(item.path)}
      >
        {item.label}
      </button>
      <br>
    {/each}
  </nav>
  
  <style>
    nav {
      display: flex;
      padding-bottom: 20px;
    }

    nav button {
      padding-left: 20px;
    }

    nav button:first-child {
      margin-right: auto;
      padding-left: 0px;
    }

  </style>