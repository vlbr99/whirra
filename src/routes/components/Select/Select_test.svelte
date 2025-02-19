<script>
  let { options, value, placeholder } = $props();
  let allOptions = $state([]);

  $effect(() => {
    allOptions = [
      { value: "0", label: placeholder },
      ...options.map((opt) =>
        typeof opt === "object" ? opt : { value: opt, label: opt }
      ),
    ];
  });
</script>

<div class="select_wrapper">
  <select bind:value class="select_component">
    {#each allOptions as option}
      <option value={option.value}>{option.label}</option>
    {/each}
  </select>
</div>

<style>
  .select_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    max-width: 650px;
    width: 100%;
  }
  .select_component {
    appearance: none;
    outline: 0;
    padding: 10px 15px;
    color: var(--secondary_color_dark);
    border-radius: 4px;
    cursor: pointer;
    background-color: var(--primary_color_dark);
    border: 1px solid var(--touch_color_dark);
  }
  .select_component::-ms-expand {
    display: none;
  }
  .select_component:focus {
    outline: 1px solid var(--secondary_color_dark);
  }
  .select_component option {
    background-color: var(--primary_color_dark);
  }
</style>
