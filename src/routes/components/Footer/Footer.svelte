<script>
  import Highlight from "svelte-highlight";
  import javascript from "svelte-highlight/languages/javascript";
  import { copy } from "svelte-copy";
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
  <footer class={className}>
      <a href="#" class="logo">Logo</a>
      <nav class="footer-nav">
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">Support</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </nav>
  </footer>
  <style>
footer {
    background-color: var(--touch_color_dark);
    padding: 15px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .logo {
    font-size: 2rem;
    font-weight: bold;
    margin: 0;
    text-decoration: none;
    color: var(--secondary_color_dark);
  }

  .footer_nav ul {
    display: flex;
    list-style-type: none;
  }

  .footer_nav li {
    margin-left: 10px;
  }

  .footer_nav a {
    color: var(--light_touch_color_dark);
    text-decoration: none;
  }

  @media (max-width: 768px) {
    .logo {
      margin-bottom: 1rem;
    }

    .footer_nav ul {
      flex-direction: column;
    }

    .footer_nav li {
      margin: 10px 0;
    }
  }
</\style>`);
</script>

<div class="footer_wrapper">
  <h1>Footer</h1>
  <p>
    A Footer is a foundational UI component that appears at the bottom of a
    webpage, providing essential information, navigation links, and other useful
    resources. It serves as the concluding section of a website, offering users
    additional guidance and support.
  </p>
  <footer>
    <a href="#" class="logo">Logo</a>
    <nav class="footer_nav">
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Support</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>
  </footer>
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
  .footer_wrapper {
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
  p {
    color: gray;
  }
  h1 {
    color: white;
  }
  footer {
    background-color: var(--touch_color_dark);
    padding: 15px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .logo {
    font-size: 2rem;
    font-weight: bold;
    margin: 0;
    text-decoration: none;
    color: var(--secondary_color_dark);
  }

  .footer_nav ul {
    display: flex;
    list-style-type: none;
  }

  .footer_nav li {
    margin-left: 10px;
  }

  .footer_nav a {
    color: var(--light_touch_color_dark);
    text-decoration: none;
  }

  @media (max-width: 768px) {
    .logo {
      margin-bottom: 1rem;
    }

    .footer_nav ul {
      flex-direction: column;
    }

    .footer_nav li {
      margin: 10px 0;
    }
  }
</style>
