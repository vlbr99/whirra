<script>
  import { fade, fly } from "svelte/transition";
  import { createEventDispatcher } from "svelte";
  let { message } = $props();

  const dispatch = createEventDispatcher();

  function close() {
    dispatch("close");
  }
</script>

{#if message}
  <div class="toast" transition:fly={{ y: 50, duration: 300 }} fade>
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
</style>
