<script>
  let { children } = $props();
  import "@fontsource-variable/geist";
  import Shell from "lucide-svelte/icons/shell";
  import LayoutGrid from "lucide-svelte/icons/layout-grid";
  import Play from "lucide-svelte/icons/play";
  import "svelte-highlight/styles/an-old-hope.css";
</script>

<header>
  <a class="logo" href="/">
    <Shell />
    <p>Whirra</p>
  </a>
  <nav>
    <a href="/dashboard">
      <Play size={22} />
      Get started</a
    >
  </nav>
</header>

{@render children()}

<style>
  :global(:root) {
    --primary_color_dark: #000000;
    --secondary_color_dark: #ffffff;
    --light_touch_color_dark: #808080;
    --touch_color_dark: #161616;
    --secondary_touch_color_dark: #222222;
  }
  :global(*) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Geist Variable", sans-serif;
  }
  :global(*::selection) {
    background-color: white !important;
    color: black;
  }
  :global(body) {
    background-color: #000000;
    overflow-x: hidden;
  }
  :global(html) {
    overflow-x: hidden;
  }
  :global(.hljs *) {
    color: #c0c0c0 !important;
  }
  :global(code) {
    background-color: transparent !important;
    color: #c0c0c0 !important;
  }
  :global(.hljs-number) {
    color: #c0c5ce;
  }
  :global(.hljs-attribute) {
    color: #c0c0c0;
  }
  :global(.hljs-string) {
    color: #c0c5ce;
  }
  :global(.hljs-attr) {
    color: #c0c5ce;
  }

  header {
    padding: 1.2rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: fixed;
    width: 100%;
    background-color: black !important;
    z-index: 99;
  }
  header .logo {
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    gap: 0.5rem;
    font-size: 1.3rem;
    text-decoration: none;
  }
  header nav {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 1rem;
  }
  header nav a {
    text-decoration: none;
    padding: 8px 16px;
    gap: 0.5rem;
    font-weight: 600;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    border: 2px solid white;
    border-radius: 8px;
    transition: 0.2s;
    margin-right: 10px;
  }
  header nav a:hover {
    border-radius: 50px;
  }
</style>
