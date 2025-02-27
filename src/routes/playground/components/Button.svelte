<script>
  let { text, onclick, className } = $props();
  export { className as class };
</script>

<button class="button {className}" {onclick}>{text}</button>

<style>
  .button {
    background-color: var(--secondary_color_dark);
    border: 0;
    padding: 10px 20px;
    border-radius: 4px;
    transition: 0.3s;
    cursor: pointer;
  }
  .button:hover {
    border-radius: 50px;
  }
</style>
