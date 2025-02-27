<script>
  let { className } = $props();
  export { className as class };
</script>

<footer class={className}>
  <a href="#" class="logo">Logo</a>
  <nav class="footer_nav">
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">Support</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
</footer>

<style>
  footer {
    background-color: var(--touch_color_dark);
    padding: 15px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .logo {
    font-size: 2rem;
    font-weight: bold;
    margin: 0;
    text-decoration: none;
    color: var(--secondary_color_dark);
  }

  .footer_nav ul {
    display: flex;
    list-style-type: none;
  }

  .footer_nav li {
    margin-left: 10px;
  }

  .footer_nav a {
    color: var(--light_touch_color_dark);
    text-decoration: none;
  }

  @media (max-width: 768px) {
    .logo {
      margin-bottom: 1rem;
    }

    .footer_nav ul {
      flex-direction: column;
    }

    .footer_nav li {
      margin: 10px 0;
    }
  }
</style>
