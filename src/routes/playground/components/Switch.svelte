<script>
  let { label, checked = $bindable(false), onChange, className } = $props();
  export { className as class };
</script>

<div class="switch_component {className}">
  <p>{label}</p>
  <label class="switch">
    <input type="checkbox" bind:checked onchange={onChange} />
    <span class="slider round"></span>
  </label>
</div>

<style>
  .switch_component {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: fit-content;
    gap: 10px;
  }
  .switch_component p {
    color: var(--secondary_color_dark);
  }
  .switch {
    position: relative;
    display: inline-block;
    width: 60px;
    height: 34px;
  }
  .switch input {
    opacity: 0;
    width: 0;
    height: 0;
  }
  .switch input:checked + .slider {
    background-color: var(--secondary_color_dark);
  }
  .switch input:checked + .slider::before {
    transform: translateX(26px);
  }
  .slider {
    position: absolute;
    cursor: pointer;
    inset: 0;
    background-color: var(--touch_color_dark);
    transition: 0.4s;
  }
  .slider::before {
    position: absolute;
    content: "";
    height: 26px;
    width: 26px;
    left: 4px;
    bottom: 4px;
    background-color: var(--primary_color_dark);
    transition: 0.4s;
  }
  .slider.round {
    border-radius: 34px;
  }
  .slider.round::before {
    border-radius: 50px;
  }
</style>
