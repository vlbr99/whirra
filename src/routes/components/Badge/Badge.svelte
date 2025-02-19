<script>
  let badge_text = $props();
  import Highlight from "svelte-highlight";
  import Copy from "lucide-svelte/icons/copy";
  import { copy } from "svelte-copy";

  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };
  import typescript from "svelte-highlight/languages/typescript";
  let code = $state(`<script>
let badge_text = $props();
<\/script>
<span class="badge">{badge_text}</span>
<style>
 .badge {
    background-color: var(--primary_bg_dark);
    color: var(--primary_color_dark);
    font-size: 0.9rem;
    padding: 4px;
    border-radius: 50px;
  }
<\/style>
`);
  let co = $state(`<Badge badge_text='badge'/>`);
  //DODATI CSS VARIJABLE I TO JE TO
</script>

<div class="badge_wrapper">
  <h1>Badge</h1>
  <p>
    A Badge is a small, attention-grabbing UI element used to highlight
    information such as notifications, statuses, or counts. It is typically
    displayed as a rounded label with a short text or number inside.
  </p>
  <div class="badges">
    <!-- <span class="badge">{badge_text}</span> -->
    <span class="badge">badge</span>
  </div>
  <div class="code_wrapper">
    <div class="hl">
      <button onclick={copy_it} use:copy={code}>Copy code</button>
      <Highlight {code} language={typescript} />
    </div>
  </div>
  <h1 style="margin-top: 20px;">Usage</h1>
  <div class="hl">
    <button onclick={copy_it} use:copy={co}>Copy code</button>
    <Highlight code={co} language={typescript} />
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
  .badge {
    background-color: var(--secondary_color_dark);
    color: var(--primary_color_dark);
    font-size: 0.9rem;
    padding: 4px;
    border-radius: 50px;
  }
  .badge_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    width: 100%;
    max-width: 650px;
    line-height: 1.5rem;
  }
  .code_wrapper {
    width: 100%;
  }
  .hl {
    background-color: #18181b;
    border-radius: 20px;
    width: 100% !important;
  }
  .badge_wrapper p {
    color: gray;
  }
  .badge_wrapper h1 {
    color: white;
  }
</style>
