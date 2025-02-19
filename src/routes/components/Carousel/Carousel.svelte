<script>
  import { Splide, SplideSlide } from "@splidejs/svelte-splide";
  import "@splidejs/svelte-splide/css";
  import { Highlight } from "svelte-highlight";
  import { javascript } from "svelte-highlight/languages";
  import { copy } from "svelte-copy";

  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };
  let code = $state(`
<script>
  import { Splide, SplideSlide } from "@splidejs/svelte-splide";
  import "@splidejs/svelte-splide/css";
<\/script>
<div class="carousel">
    <Splide aria-label="My Favorite Images">
      <SplideSlide>
        <img src="https://placehold.co/300x200" alt="Image 1" />
      </SplideSlide>
      <SplideSlide>
        <img src="https://placehold.co/300x200" alt="Image 2" />
      </SplideSlide>
    </Splide>
</div>
<style>
  .carousel img {
    width: 100%;
  }
<\/style>`);
</script>

<div class="carousel">
  <h1>Carousel</h1>
  <p>
    A Carousel is a UI component that displays multiple images, cards, or
    content items in a rotating slideshow. Users can navigate through items
    using arrows, dots, or swipe gestures, making it ideal for showcasing
    content in a compact, interactive format.
  </p>
  <p>
    Carousel from <a href="https://splidejs.com/integration/svelte-splide/"
      >Splide</a
    >
  </p>
  <div class="carousel">
    <Splide aria-label="My Favorite Images">
      <SplideSlide>
        <img src="https://placehold.co/300x200" alt="Image 1" />
      </SplideSlide>
      <SplideSlide>
        <img src="https://placehold.co/300x200" alt="Image 2" />
      </SplideSlide>
    </Splide>
  </div>
  <div class="code_wrapper">
    <h1>Usage</h1>
    <div class="hl">
      <button onclick={copy_it} use:copy={code}>Copy code</button>
      <Highlight language={javascript} {code} />
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
  .carousel {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    width: 100%;
    max-width: 650px;
    gap: 20px;
  }
  a {
    color: white;
  }
  h1 {
    color: white;
  }
  p {
    color: gray;
  }
  .carousel img {
    width: 100%;
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
