<script>
  let {
    isOpen,
    title,
    message,
    onConfirm,
    onCancel,
    children,
    className,
    b1_text,
    b2_text,
  } = $props();
  export { className as class };
</script>

{#if isOpen}
  <div class="backdrop">
    <div class="dialog {className}">
      <h2>{title}</h2>
      <p>{message}</p>
      {@render children()}
      <div class="actions">
        <button
          onclick={() => {
            onCancel();
            isOpen = false;
          }}>{b1_text}</button
        >
        <button
          onclick={() => {
            onConfirm();
            isOpen = false;
          }}>{b2_text}</button
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
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 10px;
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
</style>
