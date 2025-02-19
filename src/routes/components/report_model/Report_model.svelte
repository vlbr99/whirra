<script>
  import Highlight from "svelte-highlight";
  import typescript from "svelte-highlight/languages/typescript";
  import { copy } from "svelte-copy";

  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };
  let code = $state(`
  let reportSchema = new mongoose.Schema({
      email: {
        type: String,
        required: true,
        unique: true,
        trim: true,
        lowercase: true,
      },
      message: {
        type: String,
        required: true,
        minlength: 20,
        maxlength: 1000,
      },
  });
  //export as You like
  `);
</script>

<div class="user_model_wrapper">
  <h1>Mongoose report schema</h1>
  <p>
    The Report Schema is used to define the structure of the report data in the
    MongoDB database. It ensures that each report contains essential information
    such as the user's email and the message they submit, with proper validation
    to maintain data integrity.
  </p>
  <p class="code">
    <button onclick={copy_it} use:copy={code}>Copy code</button>
    <Highlight language={typescript} {code} />
  </p>
</div>

<style>
  button {
    padding: 5px;
    border-radius: 4px;
    background-color: white;
    cursor: pointer;
    border: 0;
    width: 80px;
    margin-left: calc(100% - 80px);
  }
  p {
    color: gray;
  }
  .user_model_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    width: 100%;
    max-width: 650px;
  }
  .user_model_wrapper h1 {
    color: white;
  }
  .code {
    background-color: #18181b;
    border-radius: 20px;
    width: 100%;
  }
</style>
