<script>
  let { text, className } = $props();
  export { className as class };
</script>

<span class="badge {className}">{text}</span>

<style>
  .badge {
    background-color: var(--secondary_color_dark);
    color: var(--primary_color_dark);
    font-size: 0.9rem;
    padding: 4px;
    border-radius: 50px;
  }
</style>
