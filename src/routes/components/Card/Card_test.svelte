<script>
  import { Highlight } from "svelte-highlight";
  import { javascript } from "svelte-highlight/languages";
  import Card from "./Card.svelte";
  import { copy } from "svelte-copy";
  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };
  let code = $state(`<script>
  let { image_url, title, price, condition, className } = $props();
  export { className as class };
</\script>

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
</\style>`);
  let code_2 = $state(`<Card
  image_url="https://placehold.co/300x200/18181b/fff"
  title="This is a very long product name that will be truncated"
  price={19.99}
  condition="new"
/>
`);
</script>

<div class="card_wrapper">
  <h1>Card</h1>
  <p>
    A Card is a versatile UI component used to display content and actions
    related to a single subject. Cards typically group related information in a
    visually distinct container, making them ideal for presenting content in an
    organized and aesthetically pleasing way.
  </p>
  <Card
    image_url="https://placehold.co/300x200/18181b/fff"
    title="This is a very long product name that will be truncated"
    price={19.99}
    condition="new"
  />
  <div class="code_wrapper">
    <h1>Usage</h1>
    <div class="hl">
      <button onclick={copy_it} use:copy={code}>Copy code</button>
      <Highlight language={javascript} {code} />
    </div>
    <div class="hl">
      <button onclick={copy_it} use:copy={code_2}>Copy code</button>
      <Highlight language={javascript} code={code_2} />
    </div>
  </div>
</div>

<style>
  button {
    width: 80px;
    background-color: white;
    border: 0;
    border-radius: 4px;
    padding: 5px;
    cursor: pointer;
    margin-left: calc(100% - 80px);
  }
  .card_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    width: 100%;
    max-width: 650px;
  }
  p {
    color: gray;
  }
  h1 {
    color: white;
  }
  .code_wrapper {
    color: white;
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    border-radius: 20px;
    display: block;
    width: 100%;
    max-width: 650px;
  }
  .hl {
    margin-top: 20px;
    background-color: #18181b;
    border-radius: 20px;
  }
</style>
