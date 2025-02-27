<script>
  import { slide } from "svelte/transition";
  let { items, className } = $props();
  export { className as class };
  let activeIndex = $state(-1);
  function toggleItem(index) {
    activeIndex = activeIndex === index ? -1 : index;
  }
</script>

<div class="accordion {className}">
  {#each items as item, index}
    <div class="accordion-item">
      <button
        class="accordion-header"
        onclick={() => toggleItem(index)}
        aria-expanded={activeIndex === index}
      >
        {item.title}
        <span class="icon">{activeIndex === index ? "−" : "+"}</span>
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
</style>
