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
  import Toast from "./Toast.svelte";
  let toastMessage = $state("");
  function showToast() {
    toastMessage = "This is a toast message!";
    setTimeout(() => {
      toastMessage = "";
    }, 3000);
  }

  function closeToast() {
    toastMessage = "";
  }
  let code = $state(`
  <script>
  import { fade, fly } from "svelte/transition";
  import { createEventDispatcher } from "svelte";
  let { message, className } = $props();
  export {className as class};
  const dispatch = createEventDispatcher();

  function close() {
    dispatch("close");
  }
<\/script>

{#if message}
  <div class="toast {className}" transition:fly={{ y: 50, duration: 300 }} fade>
    <p>{message}</p>
    <button onclick={close}>×</button>
  </div>
{/if}

<style>
  .toast {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background-color: var(--touch_color_dark);
    color: var(--secondary_color_dark);
    border: 2px solid var(--light_touch_color_dark);
    border-radius: 4px;
    padding: 12px 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    z-index: 1000;
    max-width: 300px;
  }

  .toast p {
    margin: 0;
    padding-right: 20px;
  }

  .toast button {
    background: none;
    border: none;
    font-size: 20px;
    cursor: pointer;
    color: var(--light_touch_color_dark);
    padding: 0;
    margin-left: 10px;
  }

  .toast button:hover {
    color: var(--secondary_color_dark);
  }
<\/style>`);
  let code_2 = $state(`
<script>
  let toastMessage = $state("");
  function showToast() {
    toastMessage = "This is a toast message!";
    setTimeout(() => {
      toastMessage = "";
    }, 3000);
  }

  function closeToast() {
    toastMessage = "";
  }
<\/script>
<button onclick={showToast} class="show_toast_button">Show Toast</button>
<Toast message={toastMessage} on:close={closeToast} />`);
</script>

<div class="toast_wrapper">
  <h1>Toast</h1>
  <p>
    A Toast is a lightweight, non-intrusive UI component used for displaying
    brief notifications or alerts. It typically appears at the edge of the
    screen and automatically disappears after a few seconds, making it an
    effective way to provide feedback without disrupting user interactions.
  </p>
  <button onclick={showToast} class="show_toast_button">Show Toast</button>
  <Toast message={toastMessage} on:close={closeToast} />
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
  .show_toast_button {
    background-color: white;
    border: 0;
    padding: 10px 20px;
    border-radius: 4px;
    transition: 0.3s;
    cursor: pointer;
  }
  .show_toast_button:hover {
    border-radius: 50px;
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
  .toast_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    width: 100%;
    max-width: 650px;
  }
</style>
