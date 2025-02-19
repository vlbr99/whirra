<script>
  import { copy } from "svelte-copy";

  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };
</script>

<div class="box_shadow_generator">
  <h1>Box shadows</h1>
  <p>
    Box shadows are a powerful CSS effect used to add depth and emphasis to
    elements on a webpage. By applying a shadow to an element, you can create a
    sense of layering, making your UI more visually appealing and easier to
    navigate.
  </p>
  <div class="shadow_variations">
    <div class="bs_variation_1">
      <div class="bs_1">
        <button
          onclick={copy_it}
          use:copy={`
      box-shadow:
      rgba(50, 50, 105, 0.15) 0px 2px 5px 0px,
      rgba(0, 0, 0, 0.05) 0px 1px 1px 0px;`}>Copy code</button
        >
      </div>
    </div>
    <div class="bs_variation_2">
      <div class="bs_2">
        <button
          onclick={copy_it}
          use:copy={`
            box-shadow:
            0px 2px 3px -1px rgba(0, 0, 0, 0.1),
            0px 1px 0px 0px rgba(25, 28, 33, 0.02),
            0px 0px 0px 1px rgba(25, 28, 33, 0.08);
        `}>Copy code</button
        >
      </div>
    </div>
    <div class="bs_variation_3">
      <div class="bs_3">
        <button
          onclick={copy_it}
          use:copy={`box-shadow: rgba(17, 17, 26, 0.1) 0px 0px 16px;`}
          >Copy code</button
        >
      </div>
    </div>
  </div>
</div>

<style>
  .box_shadow_generator {
    display: flex;
    align-items: flex-start;
    justify-content: flex-start;
    flex-direction: column;
    gap: 20px;
    width: 100%;
    max-width: 650px;
  }
  h1 {
    color: white;
  }
  p {
    color: gray;
  }
  .shadow_variations {
    padding: 50px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 50px;
    background-color: white;
    border-radius: 20px;
    flex-wrap: wrap;
  }
  .shadow_variations div {
    width: 250px;
    height: 250px;
    border-radius: 20px;
    background-color: white;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .shadow_variations div button {
    padding: 10px 20px;
    border-radius: 50px;
    background-color: rgb(255, 255, 255);
    border: 0;
    color: black;
    cursor: pointer;
  }
  .bs_1 {
    box-shadow:
      rgba(50, 50, 105, 0.15) 0px 2px 5px 0px,
      rgba(0, 0, 0, 0.05) 0px 1px 1px 0px;
  }
  .bs_2 {
    box-shadow:
      0px 2px 3px -1px rgba(0, 0, 0, 0.1),
      0px 1px 0px 0px rgba(25, 28, 33, 0.02),
      0px 0px 0px 1px rgba(25, 28, 33, 0.08);
  }
  .bs_3 {
    box-shadow: rgba(17, 17, 26, 0.1) 0px 0px 16px;
  }
</style>
