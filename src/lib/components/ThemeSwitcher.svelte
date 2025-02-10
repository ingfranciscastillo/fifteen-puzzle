<script>
  import Moon from "$lib/icons/moon.svelte";
  import Sun from "$lib/icons/sun.svelte";
  import { onMount } from "svelte";

  let isDarkMode = false;

  onMount(() => {
    const savedTheme = localStorage.getItem("theme");
    if (savedTheme) {
      isDarkMode = savedTheme === "dark";
      document.body.classList.toggle("dark-mode", isDarkMode);
    }
  });

  function toggleTheme() {
    isDarkMode = !isDarkMode;
    document.body.classList.toggle("dark-mode", isDarkMode);
    localStorage.setItem("theme", isDarkMode ? "dark" : "light");
  }
</script>

<button class="theme-switcher" on:click={toggleTheme}>
  {#if isDarkMode}
    <Sun />
  {:else}
    <Moon />
  {/if}
</button>

<style>
  .theme-switcher {
    cursor: pointer;
    padding: 10px;
    background-color: var(--background);
    color: var(--text);
    border: none;
    border-radius: 5px;
  }

  :global(body) {
    --background: #ededed;
    --text: #1a202c;
    background-color: var(--background);
    color: var(--text);
    transition:
      background-color 0.3s,
      color 0.3s;
  }

  :global(.dark-mode) {
    --background: #1a202c;
    --text: #ededed;
  }
</style>
