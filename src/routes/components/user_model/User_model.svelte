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
let userSchema = new mongoose.Schema({
     username: {
      type: String,
      required: true,
      unique: true,
      trim: true,
      minlength: 3,
      maxlength: 50,
    },
    email: {
      type: String,
      required: true,
      unique: true,
      trim: true,
      lowercase: true,
    },
    password: {
      type: String,
      required: true,
      minlength: 8,
      maxlength: 128,
    },
});
//export as You like
`);
</script>

<div class="user_model_wrapper">
  <h1>Mongoose user schema</h1>
  <p>
    The User Schema defines the structure of the user data in the MongoDB
    database, ensuring that all user-related information is validated before
    being stored. This schema is designed for managing basic user details such
    as the username, email, and password.
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
