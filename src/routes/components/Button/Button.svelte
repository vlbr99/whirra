<script>
  let { button_text } = $props();
  import Buttons from "./Buttons.svelte";
  import Gb from "./Gb.svelte";
  import Plus from "lucide-svelte/icons/plus";
  import Wi from "./Wi.svelte";
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
let { text, onclick } = $props();
<\/script>
<button class="button" {onclick}>{text}</button>
<style>
  .button {
    background-color: var(--secondary_color_dark);
    border: 0;
    padding: 10px 20px;
    border-radius: 4px;
    transition: 0.3s;
    cursor: pointer;
  }
  .button:hover {
    border-radius: 50px;
  }
<\/style>`);
  let code_2 = $state(
    `<Button text="Button" onclick={()=>{alert("Clicked!!!")}}/>`
  );
  let code_3 = $state(`
<script>
let { text, onclick } = $props();
<\/script>
<button class="ghost_button" {onclick}>{text}</button>
<style>
  .ghost_button {
    background-color: transparent;
    border: 1px solid var(--touch_color_dark);
    color: var(--secondary_color_dark);
    cursor: pointer;
    transition: 0.3s;
    border-radius: 4px;
    padding: 10px 20px;
  }
  .ghost_button:hover {
    background-color: var(--primary_color_dark);
    border-radius: 40px;
  }
<\/style>`);
  let code_4 = $state(
    `<Button text="Ghost Button" onclick={()=>{alert("Clicked!!!")}}/>`
  );
  let code_5 = $state(`
<script>
  let { text, icon: Icon,onclick } = $props();
<\/script>
<button class="icon_button" onclick={()=>{alert("Clicked!!!")}}>
  {#if Icon}
    <Icon />
  {/if}
  {text}</button
>
<style>
.icon_button {
    background-color: var(--secondary_color_dark);
    border: 0;
    padding: 10px 20px;
    border-radius: 4px;
    transition: 0.3s;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
  }
  .icon_button:hover {
    border-radius: 50px;
  }
<\/style>
  `);
  let code_6 =
    $state(`<Button text="With icon" icon={Plus} onclick={()=>{alert("Clicked!!!")}}/>
  //icon from lucide`);
</script>

<!-- <button class="button">{button_text}</button> -->
<div class="button_wrapper">
  <h1>Button</h1>
  <p>
    A Button is a fundamental UI element used to trigger actions or submit
    forms. It is one of the most interactive components in a user interface,
    allowing users to initiate tasks such as saving data, navigating to another
    page, or performing a specific function.
  </p>
  <Buttons
    text="Button"
    onclick={() => {
      alert("Clicked!!!");
    }}
  />
  <Gb
    text="Ghost Button"
    onclick={() => {
      alert("Clicked!!!");
    }}
  />
  <Wi
    text="With icon"
    icon={Plus}
    onclick={() => {
      alert("Clicked!!!");
    }}
  />
  <div class="code_wrapper">
    <h1>Usage</h1>
    <p>button</p>
    <div class="hl">
      <button onclick={copy_it} use:copy={code}>Copy code</button>
      <Highlight language={javascript} {code} />
    </div>
    <div class="hl">
      <button onclick={copy_it} use:copy={code_2}>Copy code</button>
      <Highlight language={javascript} code={code_2} />
    </div>
    <p>ghost button</p>
    <div class="hl">
      <button onclick={copy_it} use:copy={code_3}>Copy code</button>
      <Highlight language={javascript} code={code_3} />
    </div>
    <div class="hl">
      <button onclick={copy_it} use:copy={code_4}>Copy code</button>
      <Highlight language={javascript} code={code_4} />
    </div>
    <p>with icon</p>
    <div class="hl">
      <button onclick={copy_it} use:copy={code_5}>Copy code</button>
      <Highlight language={javascript} code={code_5} />
    </div>
    <div class="hl">
      <button onclick={copy_it} use:copy={code_6}>Copy code</button>
      <Highlight language={javascript} code={code_6} />
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
  p {
    color: gray;
    margin-top: 20px;
  }
  .button {
    background-color: var(--secondary_color_dark);
    border: 0;
    padding: 10px 20px;
    border-radius: 4px;
    transition: 0.3s;
    cursor: pointer;
  }
  .button:hover {
    border-radius: 50px;
  }
  .ghost_button {
    background-color: transparent;
    border: 1px solid var(--touch_color_dark);
    color: var(--secondary_color_dark);
    cursor: pointer;
    transition: 0.3s;
    border-radius: 4px;
    padding: 10px 20px;
  }
  .ghost_button:hover {
    background-color: var(--primary_color_dark);
    border-radius: 40px;
  }
  .icon_button {
    background-color: var(--secondary_color_dark);
    border: 0;
    padding: 10px 20px;
    border-radius: 4px;
    transition: 0.3s;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
  }
  .icon_button:hover {
    border-radius: 50px;
  }
  .button_wrapper {
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
</style>
