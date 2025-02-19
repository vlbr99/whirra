<script>
  import SelectTest from "./Select_test.svelte";
  let selectedValue = $state("0");
  const options = $state([
    { value: "1", label: "Option 1" },
    { value: "2", label: "Option 2" },
    { value: "3", label: "Option 3" },
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
  let code = $state(`
  <script>
  let { options, value, placeholder } = $props();
  let allOptions = $state([]);

  $effect(() => {
    allOptions = [
      { value: "0", label: placeholder },
      ...options.map((opt) =>
        typeof opt === "object" ? opt : { value: opt, label: opt }
      ),
    ];
  });
<\/script>

<div class="select_wrapper">
  <select bind:value class="select_component">
    {#each allOptions as option}
      <option value={option.value}>{option.label}</option>
    {/each}
  </select>
</div>

<style>
  .select_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    max-width: 650px;
    width: 100%;
  }
  .select_component {
    appearance: none;
    outline: 0;
    padding: 10px 15px;
    color: var(--secondary_color_dark);
    border-radius: 4px;
    cursor: pointer;
    background-color: var(--primary_color_dark);
    border: 1px solid var(--touch_color_dark);
  }
  .select_component::-ms-expand {
    display: none;
  }
  .select_component:focus {
    outline: 1px solid var(--secondary_color_dark);
  }
  .select_component option {
    background-color: var(--primary_color_dark);
  }
<\/style>

  `);
  let code_2 = $state(`
  <script>
      const options = $state([
    { value: "1", label: "Option 1" },
    { value: "2", label: "Option 2" },
    { value: "3", label: "Option 3" },
  ]);
  <\/script>
<Select
  {options}
  bind:value={selectedValue}
  placeholder="Choose an option"
/>`);
</script>

<div class="select_wrapper">
  <h1>Select</h1>
  <p>
    A Select component is a UI element that allows users to choose from a
    predefined list of options. It is commonly used in forms, filters, and
    settings where a dropdown selection is needed.
  </p>
  <SelectTest
    {options}
    bind:value={selectedValue}
    placeholder="Choose an option"
  />
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
  .select_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    max-width: 650px;
    width: 100%;
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
