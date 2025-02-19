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
  let {input_placeholder, input_type} = $props()
<\/script>
<input class="input" placeholder={input_placeholder} type={input_type} />
<style>
  .input {
    border: 1px solid var(--touch_color_dark);
    background-color: transparent;
    color: var(--secondary_color_dark);
    padding: 10px;
    border-radius: 5px;
  }
  .input:focus {
    outline: 1px solid var(--secondary_color_dark);
  }
<\/style>`);
  let code_2 = $state(
    `<Input input_placeholder="Input text" input_type="text"/>`
  );
</script>

<div class="input_wrapper">
  <h1>Input</h1>
  <p>
    Input fields are essential UI components that allow users to enter and
    submit data. They are commonly used in forms, search bars, login pages, and
    interactive applications.
  </p>
  <input class="input" placeholder="input text" type="text" />
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
  .input_wrapper {
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
  .input {
    border: 1px solid var(--touch_color_dark);
    background-color: transparent;
    color: var(--secondary_color_dark);
    padding: 10px;
    border-radius: 5px;
  }
  .input:focus {
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
