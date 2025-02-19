<script>
  import "@fontsource/roboto";
  import "@fontsource-variable/inter";
  import "@fontsource-variable/open-sans";
  import "@fontsource-variable/outfit";
  import "@fontsource-variable/geist";
  import { copy } from "svelte-copy";
  import Copy from "lucide-svelte/icons/copy";
  import Check from "lucide-svelte/icons/check";

  let triggerAnimation = (e) => {
    e.target.style.transform = "scale(0.5)";
    setTimeout(() => {
      e.target.style.transform = "scale(1)";
    }, 300);
  };
</script>

<div class="fonts_wrapper">
  <h1>Fonts</h1>
  <p>
    Fonts play a crucial role in UI design, shaping the readability,
    personality, and overall feel of a website or application. Choosing the
    right font enhances user experience and helps communicate the brand’s
    identity.
  </p>
  <p style="justify-content: flex-start !important;">
    Develeper favourite fonts. Fonts from <a href="https://fontsource.org/"
      >Fontsource</a
    >
  </p>
  <div class="font_divs">
    <div class="roboto">
      <p>Roboto</p>
      <span>ASDF asdf !@#$ 1234</span>
      <br />
      <p>
        npm install @fontsource/roboto
        <button use:copy={"npm install @fontsource/roboto"}
          ><Copy onclick={triggerAnimation} /></button
        >
      </p>
      <p>
        import '@fontsource/roboto';
        <button use:copy={"import '@fontsource/roboto';"}
          ><Copy onclick={triggerAnimation} /></button
        >
      </p>
      <p>
        font-family: 'Roboto', sans-serif;
        <button use:copy={"font-family: 'Roboto', sans-serif;"}
          ><Copy onclick={triggerAnimation} /></button
        >
      </p>
    </div>
    <div class="inter">
      <p>Inter</p>
      <span>ASDF asdf !@#$ 1234</span>
      <br />
      <p>
        npm install @fontsource-variable/inter
        <button use:copy={"npm install @fontsource-variable/inter"}>
          <Copy onclick={triggerAnimation} /></button
        >
      </p>
      <p>
        import '@fontsource-variable/inter';
        <button use:copy={"import '@fontsource-variable/inter';"}>
          <Copy onclick={triggerAnimation} /></button
        >
      </p>
      <p>
        font-family: 'Inter Variable', sans-serif;
        <button use:copy={"font-family: 'Inter Variable', sans-serif;"}>
          <Copy onclick={triggerAnimation} /></button
        >
      </p>
    </div>
    <div class="open_sans">
      <p>Open-sans</p>
      <span>ASDF asdf !@#$ 1234</span>
      <br />
      <p>
        npm install @fontsource-variable/open-sans
        <button use:copy={"npm install @fontsource-variable/open-sans"}>
          <Copy onclick={triggerAnimation} /></button
        >
      </p>
      <p>
        import '@fontsource-variable/open-sans';
        <button use:copy={"import '@fontsource-variable/open-sans';"}>
          <Copy onclick={triggerAnimation} /></button
        >
      </p>
      <p>
        font-family: 'Open Sans Variable', sans-serif;
        <button use:copy={"font-family: 'Open Sans Variable', sans-serif;"}>
          <Copy onclick={triggerAnimation} /></button
        >
      </p>
    </div>
    <div class="outfit">
      <p>Outfit</p>
      <span>ASDF asdf !@#$ 1234</span>
      <br />
      <p>
        npm install @fontsource-variable/outfit
        <button use:copy={"npm install @fontsource-variable/outfit"}>
          <Copy onclick={triggerAnimation} /></button
        >
      </p>
      <p>
        import '@fontsource-variable/outfit';
        <button use:copy={"import '@fontsource-variable/outfit';"}>
          <Copy onclick={triggerAnimation} /></button
        >
      </p>
      <p>
        font-family: 'Outfit Variable', sans-serif;
        <button use:copy={"font-family: 'Outfit Variable', sans-serif;"}>
          <Copy onclick={triggerAnimation} /></button
        >
      </p>
    </div>
    <div class="geist">
      <p>Geist</p>
      <span>ASDF asdf !@#$ 1234</span>
      <br />
      <p>
        npm install @fontsource-variable/geist
        <button use:copy={"npm install @fontsource-variable/geist"}>
          <Copy onclick={triggerAnimation} /></button
        >
      </p>
      <p>
        import '@fontsource-variable/geist';
        <button use:copy={"import '@fontsource-variable/geist';"}>
          <Copy onclick={triggerAnimation} /></button
        >
      </p>
      <p>
        font-family: 'Geist Variable', sans-serif;
        <button use:copy={"font-family: 'Geist Variable', sans-serif;"}>
          <Copy onclick={triggerAnimation} /></button
        >
      </p>
    </div>
  </div>
</div>

<style>
  .fonts_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    width: 100%;
    max-width: 650px;
  }
  .fonts_wrapper .font_divs {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    background-color: transparent;
  }
  .fonts_wrapper div {
    color: white;
    background-color: rgb(22, 22, 22);
    padding: 5px;
    border-radius: 10px;
    width: 100%;
  }
  .fonts_wrapper h1 {
    color: white;
    text-align: center;
  }
  .fonts_wrapper p {
    color: gray;
    display: flex;
    align-items: center;
    width: 100%;
    justify-content: space-between;
    gap: 10px;
  }
  .fonts_wrapper p button {
    background-color: transparent;
    cursor: pointer;
    border: 0;
    color: white;
  }

  .fonts_wrapper .font_divs div {
    padding: 10px;
    background-color: rgb(22, 22, 22);
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 10px;
  }
  .fonts_wrapper p a {
    color: white;
  }
  .roboto {
    font-family: "Roboto", sans-serif !important;
  }

  .roboto p {
    font-family: "Roboto", sans-serif !important;
  }

  .roboto span {
    font-family: "Roboto", sans-serif !important;
  }

  .inter {
    font-family: "Inter Variable", sans-serif !important;
  }

  .inter p {
    font-family: "Inter Variable", sans-serif !important;
  }

  .inter span {
    font-family: "Inter Variable", sans-serif !important;
  }

  .open_sans {
    font-family: "Open Sans Variable", sans-serif !important;
  }

  .open_sans p {
    font-family: "Open Sans Variable", sans-serif !important;
  }

  .open_sans span {
    font-family: "Open Sans Variable", sans-serif !important;
  }

  .outfit {
    font-family: "Outfit Variable", sans-serif !important;
  }

  .outfit p {
    font-family: "Outfit Variable", sans-serif !important;
  }

  .outfit span {
    font-family: "Outfit Variable", sans-serif !important;
  }
</style>
