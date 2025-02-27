<script>
  let { tabs, className } = $props();
  export { className as class };
  let activeTab = $state(0);

  function selectTab(index) {
    activeTab = index;
  }
</script>

<div class="tabs-container">
  <div class="tabs-header">
    {#each tabs as tab, index}
      <button
        class="tab-button"
        class:active={activeTab === index}
        onclick={() => selectTab(index)}
        aria-selected={activeTab === index}
        role="tab"
      >
        {tab.label}
      </button>
    {/each}
  </div>
  <div class="tab-content" role="tabpanel">
    {#if tabs[activeTab]}
      <div class="tab-panel">
        {tabs[activeTab].content}
      </div>
    {/if}
  </div>
</div>

<style>
  .tabs-container {
    width: min(100%, 650px);
  }

  .tabs-header {
    display: flex;
    border-bottom: 1px solid var(--touch_color_dark);
  }

  .tab-button {
    padding: 10px 20px;
    border: none;
    background-color: transparent;
    cursor: pointer;
    transition: background-color 0.3s ease;
    border-radius: 4px 4px 0 0;
    color: var(--secondary_color_dark);
  }

  .tab-button:hover {
    background-color: var(--touch_color_dark);
  }

  .tab-button.active {
    background-color: var(--touch_color_dark);
    color: var(--secondary_color_dark);
    border-bottom: none;
    margin-bottom: -1px;
  }

  .tab-content {
    background-color: var(--touch_color_dark);
    color: var(--light_touch_color_dark);
    border-top: none;
    padding: 20px;
    border-radius: 0 0 4px 4px;
  }

  .tab-panel {
    animation: fadeIn 0.3s ease;
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
</style>
