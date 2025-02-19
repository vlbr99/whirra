<script>
  let { image_url, title, price, condition } = $props();

  function truncateTitle(text, maxLength) {
    if (text.length <= maxLength) return text;
    return text.slice(0, maxLength).trim() + "...";
  }
</script>

<div class="card">
  <img
    src={image_url || "https://placehold.co/600x400/orange/white"}
    alt={title}
    class="card-image"
  />
  <h2 class="card-title">{title}</h2>
  <div class="card-footer">
    <span class="card-price">{price}$</span>
    <span class="card-condition">{condition}</span>
  </div>
</div>

<style>
  .card {
    background-color: var(--touch_color_dark);
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    display: flex;
    flex-direction: column;
    overflow: hidden;
    width: 100%;
    max-width: 300px;
    height: 315px;
  }

  .card-image {
    width: 100%;
    height: 200px;
    object-fit: cover;
    flex-shrink: 0;
  }

  .card-title {
    font-size: 1rem;
    font-weight: normal;
    margin: 1rem;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    flex-grow: 1;
    color: white;
  }

  .card-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    background-color: var(--touch_color_dark);
    flex-shrink: 0;
  }

  .card-price {
    font-weight: bold;
    font-size: 1rem;
    color: white;
  }

  .card-condition {
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
