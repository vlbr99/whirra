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
    let contactSchema = new mongoose.Schema({
        name: {
          type: String,
          required: true,
          trim: true,
          maxlength: 30,
        },
          surname: {
          type: String,
          required: true,
          trim: true,
          maxlength: 30,
        },
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
  <h1>Mongoose contact schema</h1>
  <p>
    The Contact Schema is used to define the structure of the contact form data,
    ensuring that all required fields are present and validated before storing
    them in the database. This schema manages essential contact information such
    as the user's name, surname, email, and message.
  </p>
  <p class="code">
    <button onclick={copy_it} use:copy={code}>Copy code</button>
    <Highlight language={typescript} {code} />
  </p>
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
