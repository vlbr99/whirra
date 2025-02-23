<script>
  let { href, text, target, className } = $props();
  export { className as class };
</script>

<a {href} {target} class={className}>{text}</a>

<style>
  a {
    color: var(--secondary_color_dark);
    text-decoration: none;
  }
  a:hover {
    text-decoration: underline;
  }
</style>
