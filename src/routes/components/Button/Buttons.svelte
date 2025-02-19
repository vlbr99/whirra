<script>
  let { button_text, icon: Icon } = $props();
</script>

<button class="icon_button">
  {#if Icon}
    <Icon />
  {/if}
  {button_text}</button
>

<style>
  .icon_button {
    background-color: var(--secondary_color_dark);
    border: 0;
    padding: 10px 20px;
    border-radius: 4px;
    transition: 0.3s;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
  }
  .icon_button:hover {
    border-radius: 50px;
  }
</style>
