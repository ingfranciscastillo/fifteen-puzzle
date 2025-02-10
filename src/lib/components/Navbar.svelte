<script>
  import ThemeSwitcher from "./ThemeSwitcher.svelte";
</script>

<nav class="fixed top-0 right-0 flex justify-between items-center">
  <a href="/" class="my-0 mx-4">Inicio 🏠</a>
  <a href="/how-to-play" class="my-0 mx-4">Como jugar 🕹️</a>
  <a href="/settings" class="my-0 mx-4">Ajustes ⚙️</a>
  <ThemeSwitcher />
</nav>

<style>
  nav a[href] {
    text-decoration: none;
    color: #1a202c;
  }

  nav a[href]:hover {
    color: #00995e;
  }

  :global(.dark-mode) nav a[href] {
    color: #ededed;
  }
</style>
