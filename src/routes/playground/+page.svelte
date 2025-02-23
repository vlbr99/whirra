<script>
  import "../playground/playground.scss";
  import Badge from "./components/Badge.svelte";
  import Link from "./components/Link.svelte";
</script>

<div class="wrapper_of_components">
  <Badge badge_text="new rizz" className="test" />
  <Link text="supersonic" href="https://example.com" target="_blank" className="super_link"/>
</div>

<style>
  .wrapper_of_components {
    margin-top: 100px;
    padding: 20px;
  }
</style>
