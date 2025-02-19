<script>
  let { text, icon: Icon } = $props();
</script>

<div class="micro_card">
  {#if Icon}
    <Icon />
  {/if}
  <p>{text}</p>
</div>

<style>
  .micro_card {
    padding: 10px 20px;
    background-color: var(--secondary_color_dark);
    border-radius: 5px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
  }
  .micro_card p {
    color: var(--primary_bg_dark);
  }
</style>
