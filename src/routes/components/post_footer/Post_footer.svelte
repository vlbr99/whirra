<script>
  import { Highlight } from "svelte-highlight";
  import { javascript } from "svelte-highlight/languages";
  let { postfooter_text } = $props();
  import { copy } from "svelte-copy";

  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };

  let code = $state(`
  <script>
       let { postfooter_text } = $props();
  <\/script>
   <div class="postfooter">
    <p>{postfooter_text}</p>
  </div>
  <style>
  .postfooter {
    width: 100%;
    padding: 20px;
    background-color: var(--touch_color_dark);
  }
  .postfooter p {
    text-align: center;
    color: var(--secondary_color_dark);
  }
<\/style>`);
  let code_2 =
    $state(`<PostFooter postfooter_text="Whirra - 2025. All rights reserved"/>
`);
</script>

<div class="preheader_wrapper">
  <h1>Postfooter</h1>
  <p>
    A Postfooter is a UI component that appears at the bottom of a post or
    article. It typically contains additional information, links, or actions
    related to the content, enhancing user engagement and providing further
    navigation options.
  </p>
  <!-- ZA KOMPONENTU ISPOD -->
  <!-- <p>{postfooter_text}</p> -->
  <div class="postfooter">
    <p>Whirra - 2025. All rights reserved</p>
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
    max-width: 650px;
    justify-content: center;
    flex-direction: column;
    width: 100%;
    gap: 20px;
  }
  h1 {
    color: white;
  }
  p {
    color: gray;
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
  .postfooter {
    width: 100%;
    padding: 20px;
    background-color: var(--touch_color_dark);
  }
  .postfooter p {
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
