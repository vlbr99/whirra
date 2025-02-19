<script>
  let { text, description, icon: Icon } = $props();
</script>

<div class="mini_card">
  <div class="mini_card_header">
    {#if Icon}
      <Icon />
      <p>{text}</p>
    {/if}
  </div>
  <span>{description}</span>
</div>

<style>
  .mini_card {
    padding: 10px 20px;
    background-color: var(--secondary_color_dark);
    border-radius: 5px;
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 10px;
  }
  .mini_card .mini_card_header {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    font-weight: bold;
  }
  .mini_card span {
    color: var(--primary_color_dark);
  }
</style>
