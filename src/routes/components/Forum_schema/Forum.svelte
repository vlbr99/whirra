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
let forumSchema = new mongoose.Schema({
  title: {
    type: String,
    required: true,
    trim: true,
    maxlength: 200,
  },
  content: {
    type: String,
    required: true,
    minlength: 10,
  },
  author: {
    type: String,
    required: true,
  },
  replies: [
    {
      user: { type: String,required: true },
      message: { type: String, required: true },
      createdAt: { type: Date, default: Date.now },
    },
  ],
});
//export as You like`);
</script>

<div class="user_model_wrapper">
  <h1>Mongoose Forum Schema</h1>
  <p>
    A Forum Schema in Mongoose defines the structure for storing forum-related
    data in a MongoDB database. It typically includes details about forum posts,
    such as the author, title, content, timestamps, and additional metadata to
    support discussions and interactions.
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
