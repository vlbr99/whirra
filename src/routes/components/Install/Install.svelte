<script>
  import { Highlight } from "svelte-highlight";
  import { javascript } from "svelte-highlight/languages";

  let code = $state(`<script>
  let { children } = $props();
  //add your font
  import "@fontsource-variable/geist";
</\script>
{@render children()}
<style>
:global(*) {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  /* add your font */
  font-family: "Geist Variable", sans-serif;
}
:global(:root) {
    --primary_color_dark: #000000;
    --secondary_color_dark: #ffffff;
    --light_touch_color_dark: #808080;
    --touch_color_dark: #161616;
    --secondary_touch_color_dark: #222222;
}
</\style>`);
  let env = $state(`MONGO_URI=your mongo uri`);
</script>

<div class="install_wrapper">
  <h1>Installation</h1>
  <div>
    <p>Install svelte</p>
    <span>npx sv create app-name</span>
  </div>
  <div>
    <p>Base packages</p>
    <span>npm install lucide-svelte mongoose dotenv </span>
  </div>
  <div>
    <p>Personal packages</p>
    <span
      >npm install lucide-svelte sass-embedded mongoose dotenv
      @fontsource-variable/geist
    </span>
  </div>
  <div>
    <p>
      In 'src/routes' folder create +layout.svelte file and paste the code below
    </p>
    <div class="code">
      <Highlight {code} language={javascript} />
    </div>
  </div>
  <div>
    <p>In root folder create .env file</p>
    <div class="code">
      <Highlight code={env} language={javascript} />
    </div>
  </div>
</div>

<style>
  .code {
    background-color: #18181b;
    border-radius: 20px;
    padding: 20px;
    margin-top: 10px;
  }
  .install_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
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
  span {
    color: white;
  }
</style>
