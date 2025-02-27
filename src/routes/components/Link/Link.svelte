<script>
  let { a_href, a_text } = $props();
  import Highlight from "svelte-highlight";
  import javascript from "svelte-highlight/languages/javascript";
  import Copy from "lucide-svelte/icons/copy";
  import { copy } from "svelte-copy";

  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };
  let code = $state(`
  <script>
    let { href, text, target, className } = $props();
      export { className as class };
  <\/script>
  <a {href} {target} class={className}>{text}</a>
  <style>
    a {
      color: var(--secondary_color_dark);
      text-decoration: none;
    }
    a:hover {
      text-decoration: underline;
    }
  <\/style>
`);
  let code_2 = $state(
    `<Link text="example.com" href="https://example.com" target="_blank"/>`
  );
</script>

<div class="link_wrapper">
  <h1>Link</h1>
  <p>
    A link (or hyperlink) is a fundamental UI element that allows users to
    navigate between pages, sections, or external resources. Links improve
    accessibility and usability by providing clear pathways to relevant content.
  </p>
  <a href="https://example.com" target="_blank">example.com</a>

  <div class="code_wrapper">
    <h1>Usage</h1>
    <div class="hl">
      <button onclick={copy_it} use:copy={code}>Copy code</button>
      <Highlight language={javascript} {code} />
    </div>
    <div class="hl">
      <button onclick={copy_it} use:copy={code_2}>Copy code</button>
      <Highlight language={javascript} code={code_2} />
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
  .link_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    width: 100%;
    max-width: 650px;
  }
  h1 {
    color: white;
  }
  p {
    color: gray;
  }
  /* ZA FRAMEWORK ISPOD" */
  a {
    color: var(--secondary_color_dark);
    text-decoration: none;
  }
  a:hover {
    text-decoration: underline;
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
</style>
