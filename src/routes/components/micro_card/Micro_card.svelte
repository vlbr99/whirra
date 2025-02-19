<script>
  import PackagePlus from "lucide-svelte/icons/package-plus";
  import MicroCard2 from "./Micro_card2.svelte";

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
  let { text, icon: Icon } = $props();
<\/script>

<div class="micro_card">
  {#if Icon}
    <Icon />
  {/if}
  <p>{text}</p>
</div>

<style>
  .micro_card {
    padding: 10px 20px;
    background-color: var(--secondary_color_dark);
    border-radius: 5px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
  }
  .micro_card p {
    color: var(--primary_bg_dark);
  }
<\/style>`);
  let code_2 = $state(`<MicroCard text="Micro Card" icon={PackagePlus} />
//icon from lucide`);
</script>

<div class="micro_card_wrapper">
  <h1>Micro card</h1>
  <p>
    A Micro Card is a minimal UI component featuring an icon and a heading. It
    provides a quick visual reference, making information easily scannable.
  </p>
  <div class="micro_card">
    <PackagePlus />
    <p>Micro card</p>
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
  .micro_card {
    padding: 10px 20px;
    background-color: var(--secondary_color_dark);
    border-radius: 5px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
  }
  .micro_card p {
    color: var(--primary_bg_dark);
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
