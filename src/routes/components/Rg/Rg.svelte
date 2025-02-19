<script>
  import Rg2 from "./Rg2.svelte";
  let selectedLanguage = $state("");
  let languageOptions = $state([
    { id: "html", label: "HTML" },
    { id: "css", label: "CSS" },
    { id: "javascript", label: "JavaScript" },
    { id: "svelte", label: "Svelte" },
  ]);

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
let { options, name, value = $bindable("") } = $props();
  function handleChange(event) {
    value = event.target.value;
  }
<\/script>

<form class="radio_group">
  {#each options as option}
    <div class="radio_option">
      <input
        type="radio"
        id={option.id}
        value={option.id}
        {name}
        checked={value === option.id}
        onchange={handleChange}
      />
      <label for={option.id}>{option.label}</label>
    </div>
  {/each}
</form>

<style>
  .radio_group {
    color: var(--secondary_color_dark);
  }
  .radio_group input[type="radio"] {
    accent-color: var(--touch_color_dark);
  }
  .radio_option label {
    padding-left: 15px;
  }
<\/style>`);
  let code_2 = $state(`
<script>
let selectedLanguage = $state("");
  let languageOptions = $state([
    { id: "html", label: "HTML" },
    { id: "css", label: "CSS" },
    { id: "javascript", label: "JavaScript" },
    { id: "svelte", label: "Svelte" },
]);
<\/script>
<Radio options={languageOptions} name="web" bind:value={selectedLanguage} />`);
</script>

<div class="rg_wrapper">
  <h1>Radio group</h1>
  <p>
    A Radio Group is a set of radio buttons that allows users to select a single
    option from a list of mutually exclusive choices. It is ideal for scenarios
    where only one selection is possible, such as choosing a payment method or
    selecting a preferred language.
  </p>
  <Rg2 options={languageOptions} name="web" bind:value={selectedLanguage} />
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
  .rg_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    width: 100%;
    max-width: 650px;
  }
  p {
    color: gray;
  }
  h1 {
    color: white;
  }
  .radio_group {
    color: white;
  }
  .radio_group input[type="radio"] {
    accent-color: #161616;
  }
  .radio_group label {
    padding-left: 15px;
  }
</style>
