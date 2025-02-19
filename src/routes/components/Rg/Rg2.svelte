<script>
  let { options, name, value = $bindable("") } = $props();

  function handleChange(event) {
    value = event.target.value;
  }
</script>

<form class="radio_group">
  {#each options as option}
    <div class="radio_option">
      <input
        type="radio"
        id={option.id}
        value={option.id}
        {name}
        checked={value === option.id}
        onchange={handleChange}
      />
      <label for={option.id}>{option.label}</label>
    </div>
  {/each}
</form>

<style>
  .radio_group {
    color: var(--secondary_color_dark);
  }
  .radio_group input[type="radio"] {
    accent-color: var(--touch_color_dark);
  }
  .radio_option label {
    padding-left: 15px;
  }
</style>
