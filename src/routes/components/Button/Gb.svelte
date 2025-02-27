<script>
  let { text, onclick } = $props();
</script>

<button class="ghost_button" {onclick}>{text}</button>

<style>
  .ghost_button {
    background-color: transparent;
    border: 1px solid var(--touch_color_dark);
    color: var(--secondary_color_dark);
    cursor: pointer;
    transition: 0.3s;
    border-radius: 4px;
    padding: 10px 20px;
  }
  .ghost_button:hover {
    border-radius: 40px;
  }
</style>
