<script>
  let { image_url, title, price, condition, className } = $props();
  export { className as class };
</script>

<div class="card {className}">
  <img
    src={image_url || "https://placehold.co/600x400/orange/white"}
    alt={title}
    class="card_image"
  />
  <h2 class="card_title">{title}</h2>
  <div class="card_footer">
    <span class="card_price">{price}$</span>
    <span class="card_condition">{condition}</span>
  </div>
</div>

<style>
  .card {
    background-color: var(--touch_color_dark);
    border-radius: 8px;
    display: flex;
    flex-direction: column;
    overflow: hidden;
    width: min(100%, 300px);
    height: 315px;
  }

  .card_image {
    width: 100%;
    height: 200px;
    object-fit: cover;
    flex-shrink: 0;
  }

  .card_title {
    font-size: 1rem;
    font-weight: normal;
    margin: 1rem;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    color: var(--secondary_color_dark);
  }

  .card_footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    background-color: var(--touch_color_dark);
  }

  .card_price {
    font-weight: bold;
    font-size: 1rem;
    color: var(--secondary_color_dark);
  }

  .card_condition {
    text-transform: capitalize;
    font-size: 0.9rem;
    padding: 0.25rem 0.5rem;
    border-radius: 15px;
    background-color: var(--secondary_color_dark);
  }

  @media (max-width: 768px) {
    .card {
      max-width: 100%;
    }
  }
</style>
