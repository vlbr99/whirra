<script>
  import { copy } from "svelte-copy";
  import Highlight from "svelte-highlight";
  import javascript from "svelte-highlight/languages/javascript";
  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };
  let code = $state(`
<script>
  let { className } = $props();
  export {className as class}
</\script>
<header class={className}>
   <nav>
     <div class="logo">
       <a href="index.html">Logo</a>
     </div>
     <input type="checkbox" id="menu-toggle" />
     <label for="menu-toggle" class="menu-icon">&#9776;</label>
     <ul class="menu">
       <li><a href="#">Home</a></li>
       <li><a href="#">Skills</a></li>
       <li><a href="#">Projects</a></li>
       <li><a href="#">Connect</a></li>
     </ul>
   </nav>
</header>
  <style>
    header {
    position: sticky;
    top: 0;
    width: 100%;
    background-color: var(--primary_color_dark);
    z-index: 1;
    text-decoration: none;
    list-style-type: none !important;
  }
  header nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px;
  }
  header nav #menu-toggle {
    display: none;
  }
  header nav #menu-toggle:checked ~ .menu {
    transform: scale(1, 1);
  }
  header nav .menu {
    display: flex;
    justify-content: center;
    align-items: flex-start;
  }
  header nav .menu li {
    list-style-type: none;
  }
  header nav .menu a {
    display: block;
    padding: 7px 15px;
    font-weight: 500;
    color: var(--light_touch_color_dark);
    text-decoration: none;
  }
  header .logo a {
    font-weight: bold;
    text-decoration: none;
    font-size: 1.8rem;
    color: var(--secondary_color_dark);
  }
  header .menu-icon {
    background-color: transparent !important;
    color: transparent;
  }
  @media only screen and (max-width: 950px) {
    .menu {
      flex-direction: column;
      background-color: var(--touch_color_dark);
      align-items: flex-start;
      position: absolute;
      top: 70px;
      left: 0;
      width: 100%;
      z-index: 1;
      transform: scale(1, 0);
      transform-origin: top;
      transition: transform 0.3s ease-in-out;
    }
    .menu a {
      margin-left: 15px;
    }
    .menu li {
      margin-bottom: 10px;
    }
    .menu-icon {
      display: block;
      color: var(--secondary_color_dark) !important;
      font-size: 28px;
      cursor: pointer;
      background-color: var(--secondary_color_dark) !important;
    }
  }
</\style>`);
</script>

<div class="header_wrapper">
  <h1>Header</h1>
  <p>
    A Header is a key UI component located at the top of a webpage, providing
    essential navigation, branding, and quick access to important sections. It
    acts as the starting point for users to explore the website.
  </p>
  <header>
    <nav>
      <div class="logo">
        <a href="index.html">Logo</a>
      </div>
      <input type="checkbox" id="menu-toggle" />
      <label for="menu-toggle" class="menu-icon">&#9776;</label>
      <ul class="menu">
        <li><a href="#">Home</a></li>
        <li><a href="#">Skills</a></li>
        <li><a href="#">Projects</a></li>
        <li><a href="#">Connect</a></li>
      </ul>
    </nav>
  </header>
  <div class="code_wrapper">
    <h1>Usage</h1>
    <div class="hl">
      <button onclick={copy_it} use:copy={code}>Copy code</button>
      <Highlight language={javascript} {code} />
    </div>
  </div>
</div>

<style>
  button {
    width: 80px;
    background-color: white;
    border: 0;
    border-radius: 4px;
    padding: 5px;
    cursor: pointer;
    margin-left: calc(100% - 80px);
  }
  .header_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    width: 100%;
    max-width: 650px;
  }
  .code_wrapper {
    color: white;
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    border-radius: 20px;
    display: block;
    width: 100%;
    max-width: 650px;
  }
  .hl {
    margin-top: 20px;
    background-color: #18181b;
    border-radius: 20px;
  }
  h1 {
    color: white;
  }
  p {
    color: gray;
  }
  header {
    position: sticky;
    top: 0;
    width: 100%;
    background-color: var(--primary_color_dark);
    z-index: 1;
    text-decoration: none;
    list-style-type: none !important;
  }
  header nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px;
  }
  header nav #menu-toggle {
    display: none;
  }
  header nav #menu-toggle:checked ~ .menu {
    transform: scale(1, 1);
  }
  header nav .menu {
    display: flex;
    justify-content: center;
    align-items: flex-start;
  }
  header nav .menu li {
    list-style-type: none;
  }
  header nav .menu a {
    display: block;
    padding: 7px 15px;
    font-weight: 500;
    color: var(--light_touch_color_dark);
    text-decoration: none;
  }
  header .logo a {
    font-weight: bold;
    text-decoration: none;
    font-size: 1.8rem;
    color: var(--secondary_color_dark);
  }
  header .menu-icon {
    background-color: transparent !important;
    color: transparent;
  }
  @media only screen and (max-width: 950px) {
    .menu {
      flex-direction: column;
      background-color: var(--touch_color_dark);
      align-items: flex-start;
      position: absolute;
      top: 70px;
      left: 0;
      width: 100%;
      z-index: 1;
      transform: scale(1, 0);
      transform-origin: top;
      transition: transform 0.3s ease-in-out;
    }
    .menu a {
      margin-left: 15px;
    }
    .menu li {
      margin-bottom: 10px;
    }
    .menu-icon {
      display: block;
      color: var(--secondary_color_dark) !important;
      font-size: 28px;
      cursor: pointer;
      background-color: var(--secondary_color_dark) !important;
    }
  }
</style>
