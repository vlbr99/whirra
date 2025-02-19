<script>
  import { Highlight } from "svelte-highlight";
  import { javascript } from "svelte-highlight/languages";
  let { preheader_text } = $props();
  import { copy } from "svelte-copy";

  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };
  let code = $state(`
  <script>
       let { preheader_text } = $props();
  <\/script>
   <div class="preheader">
    <p>{preheader_text}</p>
  </div>
  <style>
  .preheader {
    width: 100%;
    padding: 20px;
    background-color: var(--touch_color_dark);
  }
  .preheader p {
    text-align: center;
    color: var(--secondary_color_dark);
  }
<\/style>`);
  let code_2 =
    $state(`<Preheader preheader_text="Default preheader content - customize as needed."/>
`);
</script>

<div class="preheader_wrapper">
  <h1>Preheader</h1>
  <p>
    A Preheader is a small text component that appears above the main heading or
    content. It provides context, highlights key information, or introduces a
    section in a subtle way.
  </p>
  <!-- ZA KOMPONENTU ISPOD -->
  <!-- <p>{preheader_text}</p> -->
  <div class="preheader">
    <p>Default preheader content - customize as needed.</p>
  </div>
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
  .preheader_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    width: 100%;
    max-width: 650px;
    gap: 20px;
  }
  button {
    padding: 5px;
    border-radius: 4px;
    background-color: white;
    cursor: pointer;
    border: 0;
    width: 80px;
    margin-left: calc(100% - 80px);
  }
  h1 {
    color: white;
  }
  p {
    color: gray;
  }
  .preheader {
    width: 100%;
    padding: 20px;
    background-color: var(--touch_color_dark);
  }
  .preheader p {
    text-align: center;
    color: var(--secondary_color_dark);
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
