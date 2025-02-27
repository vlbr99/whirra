<script>
  import { slide } from "svelte/transition";
  let { items } = $props();
  let activeIndex = $state(-1);
  function toggleItem(index) {
    activeIndex = activeIndex === index ? -1 : index;
  }

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
  import { slide } from "svelte/transition";
  let { items, className } = $props();
  export { className as class };
  let activeIndex = $state(-1);
  function toggleItem(index) {
    activeIndex = activeIndex === index ? -1 : index;
  }
<\/script>
<div class="accordion {className}">
  {#each items as item, index}
    <div class="accordion-item">
      <button
        class="accordion-header"
        onclick={() => toggleItem(index)}
        aria-expanded={activeIndex === index}
      >
        {item.title}
        <span class="icon">{activeIndex === index ? "-" : "+"}</span>
      </button>
      {#if activeIndex === index}
        <div class="accordion-content" transition:slide>
          {item.content}
        </div>
      {/if}
    </div>
  {/each}
</div>
<style>
  .accordion {
    width: min(100%, 650px);
  }
  .accordion-item {
    border: 1px solid var(--touch_color_dark);
    margin-bottom: -1px;
    overflow: hidden;
  }
  .accordion-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    padding: 1rem;
    background-color: var(--touch_color_dark);
    border: none;
    text-align: left;
    cursor: pointer;
    color: var(--secondary_color_dark);
  }
  .accordion-item:last-child {
    border-radius: 0 0 10px 10px;
  }
  .accordion-item:first-child {
    border-radius: 10px 10px 0 0;
  }
  .accordion-header:hover {
    background-color: var(--secondary_touch_color_dark);
  }
  .icon {
    font-size: 1.2rem;
  }
  .accordion-content {
    padding: 1rem;
    background-color: var(--secondary_touch_color_dark);
    color: var(--light_touch_color_dark);
  }
<\/style>
`);
  let code_2 = $state(`
<script>
  const accordionItems = $state([
    { title: "Section 1", content: "Content for section 1" },
    { title: "Section 2", content: "Content for section 2" },
    { title: "Section 3", content: "Content for section 3" },
]);
<\/script>

<Accordion items={accordionItems} />`);
</script>

<div class="ac_wrapper">
  <h1>Accordion</h1>
  <p>
    An Accordion is a UI component that organizes content into collapsible
    sections. Each section can be expanded or collapsed individually, allowing
    users to toggle visibility of content and save screen space while providing
    quick access to detailed information.
  </p>
  <div class="accordion">
    {#each items as item, index}
      <div class="accordion-item">
        <button
          class="accordion-header"
          onclick={() => toggleItem(index)}
          aria-expanded={activeIndex === index}
        >
          {item.title}
          <span class="icon">{activeIndex === index ? "-" : "+"}</span>
        </button>
        {#if activeIndex === index}
          <div class="accordion-content" transition:slide>
            {item.content}
          </div>
        {/if}
      </div>
    {/each}
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
  .ac_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    max-width: 650px;
    width: 100%;
  }
  h1 {
    color: white;
  }
  p {
    color: gray;
  }
  .accordion {
    width: 100%;
    max-width: 650px;
  }

  .accordion-item {
    border: 1px solid var(--touch_color_dark);
    margin-bottom: -1px;
    overflow: hidden;
  }

  .accordion-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    padding: 1rem;
    background-color: var(--touch_color_dark);
    border: none;
    text-align: left;
    cursor: pointer;
    transition: background-color 0.3s ease;
    color: var(--secondary_color_dark);
  }
  .accordion-item:last-child {
    border-radius: 0 0 10px 10px;
  }
  .accordion-item:first-child {
    border-radius: 10px 10px 0 0;
  }
  .accordion-header:hover {
    background-color: var(--secondary_touch_color_dark);
  }

  .icon {
    font-size: 1.2rem;
  }

  .accordion-content {
    padding: 1rem;
    background-color: var(--secondary_touch_color_dark);
    color: var(--light_touch_color_dark);
  }
</style>
