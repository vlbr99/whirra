<script>
  import PackagePlus from "lucide-svelte/icons/package-plus";
  import MiniCard2 from "./MiniCard2.svelte";
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
  let { text, description, icon: Icon, className } = $props();
  export { className as class };
<\/script>

<div class="mini_card {className}">
  <div class="mini_card_header">
    {#if Icon}
      <Icon />
      <p>{text}</p>
    {/if}
  </div>
  <span>{description}</span>
</div>

<style>
  .mini_card {
    padding: 10px 20px;
    background-color: var(--secondary_color_dark);
    border-radius: 5px;
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 10px;
  }
  .mini_card .mini_card_header {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    font-weight: bold;
  }
  .mini_card span {
    color: var(--primary_color_dark);
  }
<\/style>`);
  let code_2 = $state(`<MiniCard
    text="mini card"
    description="Some mini card content"
    icon={PackagePlus}
  />
  //icon from lucide`);
</script>

<div class="micro_card_wrapper">
  <h1>Mini card</h1>
  <p>
    A mini Card is a compact UI component that combines an icon, a heading, and
    a short description. It is designed to present key information in a visually
    appealing and concise way.
  </p>
  <MiniCard2
    text="mini card"
    description="Some mini card content"
    icon={PackagePlus}
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
  .micro_card_wrapper {
    display: flex;
    align-items: flex-start;
    width: 100%;
    max-width: 650px;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
  }
  h1 {
    color: white;
  }
  p {
    color: gray;
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
