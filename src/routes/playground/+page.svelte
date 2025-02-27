<script>
  import "../playground/playground.scss";
  import Ad from "./components/Ad.svelte";
  import Badge from "./components/Badge.svelte";
  import Link from "./components/Link.svelte";
  import Button from "./components/Button.svelte";
  import Footer from "./components/Footer.svelte";
  import Cb from "./components/Cb.svelte";
  import T from "./components/T.svelte";
  import I from "./components/I.svelte";
  import Acc from "./components/Acc.svelte";
  import Switch from "./components/Switch.svelte";
  import Radio from "./components/Radio.svelte";
  import Tabs from "./components/Tabs.svelte";
  import Op from "./components/Op.svelte";
  let input_value = $state("");
  let tarea = $state("");
  $effect(() => {
    console.log(selectedValue);
  });
  const accordionItems = $state([
    { title: "Section 1", content: "Content for section 1" },
    { title: "Section 2", content: "Content for section 2" },
    { title: "Section 3", content: "Content for section 3" },
  ]);
  let selectedLanguage = $state("");
  let languageOptions = $state([
    { id: "html", label: "HTML" },
    { id: "css", label: "CSS" },
    { id: "javascript", label: "JavaScript" },
    { id: "svelte", label: "Svelte" },
  ]);
  $effect(() => {
    if (selectedLanguage == "html") {
      console.log("klik");
    } else {
      console.log("nema");
    }
  });

  const tabsData = $state([
    { label: "Tab 1", content: "This is the content for Tab 1" },
    { label: "Tab 2", content: "Here is the content for Tab 2" },
    { label: "Tab 3", content: "And this is what you see in Tab 3" },
  ]);
  //dia
  let showDialog = $state(false);

  function handleConfirm() {
    showDialog = false;
  }

  function handleCancel() {
    showDialog = true;
  }
  $effect(() => {
    if (!showDialog) {
      showDialog = false;
    }
  });
  let selectedValue = $state("0");
  const options = $state([
    { value: "1", label: "Option 1" },
    { value: "2", label: "Option 2" },
    { value: "3", label: "Option 3" },
  ]);
</script>

<div class="wrapper_of_components">
  <Op
    {options}
    bind:value={selectedValue}
    placeholder="Choose an option"
    onchange={(e) => {
      selectedValue = e.target.value;
      console.log(selectedValue);
    }}
  />
  {#if showDialog}
    <Ad
      b1_text="Close"
      b2_text="Skibidi"
      bind:isOpen={showDialog}
      title="Delete Item"
      message="Are you sure you want to delete this item?"
      onConfirm={() => {
        handleConfirm();
        showDialog = false;
      }}
      onCancel={() => {
        handleCancel();
        showDialog = false;
      }}
    >
      <p>some children content</p>
    </Ad>
  {/if}
  <Tabs tabs={tabsData} />
  <Radio options={languageOptions} name="web" bind:value={selectedLanguage} />
  <Badge text="new rizz" className="test" />
  <Link
    text="supersonic"
    href="https://example.com"
    target="_blank"
    className="super_link"
  />
  <Button
    text="test"
    className="supersonic"
    onclick={() => {
      showDialog = true;
    }}
  />
  <Cb label="PRIFATAM" className="tteess" />
  <T placeholder="simne" className="test" bind:value={tarea} />
  <I placeholder="test" type="text" bind:value={input_value} />
  <Button
    text="op"
    onclick={() => {
      console.log(tarea);
    }}
  />
  <Acc items={accordionItems} />
  <Switch label="AVION mode" />
  <Footer />
</div>

<style>
  .wrapper_of_components {
    margin-top: 100px;
    padding: 20px;
  }
</style>
