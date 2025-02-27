<script>
  let { placeholder, type, className, value = $bindable() } = $props();
  export { className as class };
</script>

<input class={className} {placeholder} {type} bind:value />

<style>
  input {
    border: 1px solid var(--touch_color_dark);
    background-color: transparent;
    color: var(--secondary_color_dark);
    padding: 10px;
    border-radius: 5px;
  }
  input:focus {
    outline: 1px solid var(--secondary_color_dark);
  }
</style>
