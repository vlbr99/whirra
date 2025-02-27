<script>
  let { checked, label, className } = $props();
  export { className as class };
</script>

<label class="checkbox {className}">
  <input type="checkbox" bind:checked />
  <span>{label}</span>
</label>

<style>
  .checkbox {
    color: var(--secondary_color_dark);
    display: flex;
    align-items: center;
  }
  .checkbox input[type="checkbox"] {
    accent-color: var(--secondary_color_dark);
    background-color: transparent;
    margin-right: 5px;
  }
</style>
