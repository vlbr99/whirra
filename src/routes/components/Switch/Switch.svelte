<script>
  import SwitchTest from "./Switch_test.svelte";
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
  let { label, checked = $bindable(false), onChange } = $props();
<\/script>

<div class="switch_component">
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
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
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
<\/style>`);

  let code_2 = $state(`
<script>
  let airplaneMode = $state(false);
  let handleAirplaneModeChange = () => {
    console.log("Airplane mode:", airplaneMode);
  };
<\/script>

<Switch
  label="Airplane mode"
  bind:checked={airplaneMode}
  onChange={handleAirplaneModeChange}
/>`);
  let airplaneMode = $state(false);
  let handleAirplaneModeChange = () => {
    console.log("Airplane mode:", airplaneMode);
  };
</script>

<div class="cb">
  <h1>Switch</h1>
  <p>
    A Switch is a UI component used to toggle between two states, such as on/off
    or enabled/disabled. It provides a clear and intuitive way to control
    settings and preferences.
  </p>
  <SwitchTest
    label="Airplane mode"
    bind:checked={airplaneMode}
    onChange={handleAirplaneModeChange}
  />
  <p>Airplane mode is {airplaneMode ? "ON" : "OFF"}</p>
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
  button {
    width: 80px;
    background-color: white;
    border: 0;
    border-radius: 4px;
    padding: 5px;
    cursor: pointer;
    margin-left: calc(100% - 80px);
  }
  .cb {
    display: flex;
    align-items: flex-start;
    width: 100%;
    max-width: 650px;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
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
  .hl {
    margin-top: 20px;
    background-color: #18181b;
    border-radius: 20px;
  }
</style>
