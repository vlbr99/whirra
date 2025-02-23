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
  <footer>
    <div class="footer-content">
      <a href="#" class="logo">Logo</a>
      <nav class="footer-nav">
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">Support</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </nav>
    </div>
  </footer>
  <style>
   footer {
    background-color: var(--touch_color_dark);
    padding: 2rem 0;
    width: 100%;
  }

  .footer-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1rem;
  }

  .logo {
    font-size: 1.5rem;
    font-weight: bold;
    margin: 0;
    text-decoration: none;
    color: var(--secondary_color_dark);
  }

  .footer-nav ul {
    display: flex;
    list-style-type: none;
    padding: 0;
    margin: 0;
  }

  .footer-nav li {
    margin-left: 1.5rem;
  }

  .footer-nav a {
    color: var(--light_touch_color_dark);
    text-decoration: none;
  }

  .footer-nav a:hover {
    text-decoration: underline;
  }

  @media (max-width: 768px) {
    .footer-content {
      flex-direction: column;
      align-items: center;
      text-align: center;
    }

    .logo {
      margin-bottom: 1rem;
    }

    .footer-nav ul {
      flex-direction: column;
    }

    .footer-nav li {
      margin: 0.5rem 0;
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
    <div class="footer-content">
      <a href="#" class="logo">Logo</a>
      <nav class="footer-nav">
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">Support</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </nav>
    </div>
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
    padding: 2rem 0;
    width: 100%;
  }

  .footer-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1rem;
  }

  .logo {
    font-size: 1.5rem;
    font-weight: bold;
    margin: 0;
    text-decoration: none;
    color: var(--secondary_color_dark);
  }

  .footer-nav ul {
    display: flex;
    list-style-type: none;
    padding: 0;
    margin: 0;
  }

  .footer-nav li {
    margin-left: 1.5rem;
  }

  .footer-nav a {
    color: var(--light_touch_color_dark);
    text-decoration: none;
  }

  .footer-nav a:hover {
    text-decoration: underline;
  }

  @media (max-width: 768px) {
    .footer-content {
      flex-direction: column;
      align-items: center;
      text-align: center;
    }

    .logo {
      margin-bottom: 1rem;
    }

    .footer-nav ul {
      flex-direction: column;
    }

    .footer-nav li {
      margin: 0.5rem 0;
    }
  }
</style>
