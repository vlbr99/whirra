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
  import Tabs from "./Tabs.svelte";

  const tabsData = $state([
    { label: "Tab 1", content: "This is the content for Tab 1" },
    { label: "Tab 2", content: "Here is the content for Tab 2" },
    { label: "Tab 3", content: "And this is what you see in Tab 3" },
  ]);

  let code = $state(`
  <script>
  let { tabs } = $props();
  let activeTab = $state(0);

  function selectTab(index) {
    activeTab = index;
  }
</\script>

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
    width: 100%;
    max-width: 650px;
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
</\style>`);
  let code_2 = $state(`const tabsData = $state([
    { label: "Tab 1", content: "This is the content for Tab 1" },
    { label: "Tab 2", content: "Here is the content for Tab 2" },
    { label: "Tab 3", content: "And this is what you see in Tab 3" },
  ]);
  <Tabs tabs={tabsData} />
`);
</script>

<div class="tabs_wrapper">
  <h1>Tabs</h1>
  <p>
    A Tabs component is a UI element that allows users to navigate between
    different sections of content within the same container. Each tab
    corresponds to a specific content area, and clicking on a tab displays its
    associated content while hiding the rest.
  </p>
  <Tabs tabs={tabsData} />
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
    padding: 5px;
    border-radius: 4px;
    background-color: white;
    cursor: pointer;
    border: 0;
    width: 80px;
    margin-left: calc(100% - 80px);
  }
  .tabs_wrapper {
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
