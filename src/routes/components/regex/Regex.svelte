<script>
  import "../regex/regex.scss";
  import { copy } from "svelte-copy";

  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };
</script>

<div class="regex_wrapper">
  <h1>Regex snippets</h1>
  <p>
    Regular Expressions (Regex) are powerful tools for searching, matching, and
    manipulating text. In web development, they are used for tasks such as form
    validation, searching through data, and replacing text patterns. Below are
    some common Regex snippets you can use in your projects.
  </p>
  <div>
    <p>
      <b>Username:</b> length: 3-30, no spaces allowed, no special characters
    </p>
    <span>^[a-zA-Z0-9]{(3, 30)}$</span>
    <button onclick={copy_it} use:copy={`^[a-zA-Z0-9]{(3, 30)}$`}
      >Copy code</button
    >
  </div>
  <div>
    <p>
      <b>Email:</b> regular email validation regex
    </p>
    <span
      >^&#123;a-zA-Z0-9._%+-&#125;+@[a-zA-Z0-9.-]+\.[a-zA-Z]&#123;2,&#125;$</span
    >
    <button
      onclick={copy_it}
      use:copy={`^&#123;a-zA-Z0-9._%+-&#125;+@[a-zA-Z0-9.-]+\.[a-zA-Z]&#123;2,&#125;$`}
      >Copy code</button
    >
  </div>
  <div>
    <p>
      <b>URL:</b> regular URL validation regex
    </p>
    <span
      >^(https?:\/\/)?(www\.)?[a-zA-Z0-9-]+\.[a-zA-Z]&#123;2,&#125;(/.*)?$
    </span>
    <button
      onclick={copy_it}
      use:copy={`^(https?:\/\/)?(www\.)?[a-zA-Z0-9-]+\.[a-zA-Z]&#123;2,&#125;(/.*)?$`}
      >Copy code</button
    >
  </div>
</div>

<style>
  button {
    padding: 5px;
    border-radius: 4px;
    background-color: white;
    cursor: pointer;
    border: 0;
    width: 80px;
  }
</style>
