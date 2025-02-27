<script>
  import { Highlight } from "svelte-highlight";
  import { javascript } from "svelte-highlight/languages";
  import { copy } from "svelte-copy";

  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };
  let code = $state(`
<script>
  let { placeholder, className, value = $bindable() } = $props();
  export { className as class };
<\/script>
<textarea class={className} {placeholder} bind:value></textarea>
<style>
   textarea {
    resize: vertical;
    color: var(--secondary_color_dark);
    background-color: transparent;
    border: 1px solid var(--touch_color_dark);
    border-radius: 8px;
    padding: 5px 10px;
  }
  textarea:focus {
    outline: 1px solid var(--secondary_color_dark);
  }
<\/style>`);
  let code_2 = $state(`
<script>
  let textarea_value = $state("")
<\/script>
<Textarea placeholder="textarea" bind:value={textarea_value}/>`);
</script>

<div class="textarea_wrapper">
  <h1>Textarea</h1>
  <p>
    A Textarea is a UI component that allows users to input multi-line text. It
    is commonly used in forms, comments, messaging, and content creation fields.
  </p>
  <textarea class="textarea" placeholder="textarea"></textarea>
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
  h1 {
    color: white;
  }
  p {
    color: gray;
  }
  .textarea_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    width: 100%;
    max-width: 650px;
  }
  .textarea {
    resize: vertical;
    color: var(--secondary_color_dark);
    background-color: transparent;
    border: 1px solid var(--touch_color_dark);
    border-radius: 8px;
    padding: 5px 10px;
  }
  .textarea:focus {
    outline: 1px solid var(--secondary_color_dark);
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
