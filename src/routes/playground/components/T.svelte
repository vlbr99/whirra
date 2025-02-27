<script>
  let { placeholder, className, value = $bindable() } = $props();
  export { className as class };
</script>

<textarea class={className} {placeholder} bind:value></textarea>

<style>
  textarea {
    resize: vertical;
    color: var(--secondary_color_dark);
    background-color: transparent;
    border: 1px solid var(--touch_color_dark);
    border-radius: 8px;
    padding: 5px 10px;
  }
  textarea:focus {
    outline: 1px solid var(--secondary_color_dark);
  }
</style>
