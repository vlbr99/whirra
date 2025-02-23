<script>
  import { Highlight } from "svelte-highlight";
  import { javascript } from "svelte-highlight/languages";
  import { copy } from "svelte-copy";

  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };
  let code = $state(`<script>
  let { children } = $props();
  //add your font
  import "@fontsource-variable/geist";
</\script>
{@render children()}
<style>
  :global(:root) {
    --primary_color_dark: #000000;
    --secondary_color_dark: #ffffff;
    --light_touch_color_dark: #808080;
    --touch_color_dark: #161616;
    --secondary_touch_color_dark: #222222;
  }
  :global(*) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Geist Variable", sans-serif;
  }
  :global(*::selection) {
    background-color: var(--secondary_color_dark) !important;
    color: var(--primary_color_dark);
  }
  :global(body) {
    background-color: var(--primary_color_dark);
    overflow-x: hidden;
  }
  :global(html) {
    overflow-x: hidden;
  }
</\style>`);
  let env = $state(`MONGO_URI=your mongo uri`);
</script>

<div class="install_wrapper">
  <h1>Installation</h1>
  <div>
    <p>Install svelte</p>
    <span>npx sv create app-name</span>
    <button onclick={copy_it} use:copy={"npx sv create app-name"}
      >Copy code</button
    >
  </div>
  <div>
    <p>Base packages</p>
    <span>npm install lucide-svelte mongoose dotenv</span>
    <button
      onclick={copy_it}
      use:copy={"npm install lucide-svelte mongoose dotenv"}>Copy code</button
    >
  </div>
  <div>
    <p>Personal packages</p>
    <span
      >npm install lucide-svelte sass-embedded mongoose dotenv
      @fontsource-variable/geist
    </span>
    <button
      onclick={copy_it}
      use:copy={"npm install lucide-svelte sass-embedded mongoose dotenv @fontsource-variable/geist"}
      >Copy code</button
    >
  </div>
  <div>
    <p>
      In 'src/routes' folder create +layout.svelte file and paste the code below
    </p>
    <div class="code">
      <button onclick={copy_it} use:copy={code}>Copy code</button>
      <Highlight {code} language={javascript} />
    </div>
  </div>
  <div>
    <p>In root folder create .env file</p>
    <div class="code">
      <button onclick={copy_it} use:copy={env}>Copy code</button>
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
  button {
    background-color: white;
    color: black;
    border-radius: 4px;
    border: 0;
    padding: 5px;
    width: 80px;
    cursor: pointer;
    float: right;
  }
</style>
