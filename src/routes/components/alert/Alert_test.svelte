<script>
  import Alert from "./Alert.svelte";
  let showDialog = $state(false);

  function handleConfirm() {
    showDialog = false;
  }

  function handleCancel() {
    showDialog = true;
  }
  $effect(() => {
    if (!showDialog) {
      showDialog = false;
    }
  });

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
    let { isOpen, title, message, onConfirm, onCancel, children } = $props();
<\/script>

{#if isOpen}
  <div
    class="backdrop">
    <div
      class="dialog">
      <h2>{title}</h2>
      <p>{message}</p>
      <div class="actions">
        <button
          onclick={() => {
            onCancel();
            isOpen = false;
          }}>Cancel</button
        >
        <button
          onclick={() => {
            onConfirm();
            isOpen = false;
          }}>OK</button
        >
      </div>
    </div>
  </div>
{/if}

<style>
  .backdrop {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1000;
  }

  .dialog {
    background: var(--touch_color_dark);
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    width: 400px;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
  }

  .actions {
    margin-top: 1rem;
    display: flex;
    justify-content: flex-end;
    gap: 10px;
  }
  h2 {
    color: var(--secondary_color_dark);
  }
  p {
    color: var(--light_touch_color_dark);
  }
  button {
    background-color: var(--secondary_color_dark);
    border: 0;
    padding: 10px 20px;
    border-radius: 4px;
    transition: 0.3s;
    cursor: pointer;
  }
<\/style>

  `);
  let code_2 = $state(`
<script>
let showDialog = $state(false);

  function handleConfirm() {
    showDialog = false;
  }

  function handleCancel() {
    showDialog = true;
  }
  $effect(() => {
    if (!showDialog) {
      showDialog = false;
    }
  });
<\/script>
{#if showDialog}
  <Alert
    bind:isOpen={showDialog}
    title="Delete Item"
    message="Are you sure you want to delete this item?"
    onConfirm={() => {
      handleConfirm();
      showDialog = false;
    }}
    onCancel={() => {
      handleCancel();
      showDialog = false;
    }}
  >
    <p>some children content</p>
  </Alert>
{/if}
<style>
  button {
    background-color: var(--secondary_color_dark);
    border: 0;
    padding: 10px 20px;
    border-radius: 4px;
    transition: 0.3s;
    cursor: pointer;
  }
<\/style>`);
</script>

<div class="ad_wrapper">
  <h1>Alert dialog</h1>
  <p>
    An Alert Dialog is a UI component used to capture user attention by
    displaying important messages, warnings, or confirmation requests. Unlike
    toast notifications, alert dialogs require user interaction before they can
    be dismissed, making them ideal for critical actions.
  </p>
  <button onclick={() => (showDialog = true)}>Open Alert</button>
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

{#if showDialog}
  <Alert
    bind:isOpen={showDialog}
    title="Delete Item"
    message="Are you sure you want to delete this item?"
    onConfirm={() => {
      handleConfirm();
      showDialog = false;
    }}
    onCancel={() => {
      handleCancel();
      showDialog = false;
    }}
  >
    <p>some children content</p>
  </Alert>
{/if}

<style>
  button {
    background-color: var(--secondary_color_dark);
    border: 0;
    padding: 10px 20px;
    border-radius: 4px;
    transition: 0.3s;
    cursor: pointer;
  }

  .ad_wrapper {
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
  .ad_wrapper button {
    margin-top: 20px;
    margin-bottom: 20px;
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
  .code_wrapper button {
    width: 80px;
    background-color: white;
    border: 0;
    border-radius: 4px;
    padding: 5px;
    cursor: pointer;
    margin-left: calc(100% - 80px);
    margin-top: 0 !important;
    margin-bottom: 0 !important;
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
</style>
