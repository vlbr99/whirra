<script>
  import Cb2 from "./Cb2.svelte";
  let isAgreed = $state(false);

  import { Highlight } from "svelte-highlight";
  import { javascript } from "svelte-highlight/languages";
  import { copy } from "svelte-copy";

  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };

  let code = $state(`<script>
  let { checked, label } = $props();
<\/script>

<label class="checkbox">
  <input type="checkbox" bind:checked />
  <span>{label}</span>
</label>

<style>
  .checkbox {
    color: var(--secondary_color_dark);
    display: flex;
    align-items: center;
  }
  .checkbox input[type="checkbox"] {
    accent-color: var(--secondary_color_dark);
    background-color: transparent;
    margin-right: 5px;
  }
<\/style>`);
  let code_2 = $state(`<Checkbox bind:checked={isAgreed} label="I agree" />`);
</script>

<div class="cb_wrapper">
  <h1>Checkbox</h1>
  <p>
    A checkbox is a UI element that allows users to select one or multiple
    options from a list. It is commonly used in forms, settings, and filters
    where multiple selections are needed.
  </p>
  <Cb2 bind:checked={isAgreed} label="I agree" />
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
  .code_wrapper button {
    width: 80px;
    background-color: white;
    border: 0;
    border-radius: 4px;
    padding: 5px;
    cursor: pointer;
    margin-left: calc(100% - 80px);
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
  .cb_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    max-width: 650px;
    width: 100%;
  }
</style>
