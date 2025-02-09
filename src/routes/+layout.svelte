<script lang="ts">
  import Navbar from "$lib/components/Navbar.svelte";

  let { children } = $props();
  import "../app.css";
  import "../fonts.css";
</script>

<Navbar />

{@render children()}

<style>
  :global(body) {
    font-family: "Satoshi-Regular", sans-serif;
  }
</style>
