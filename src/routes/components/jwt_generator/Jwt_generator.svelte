<script>
  import "../jwt_generator/jwt.scss";
  import Wrench from "lucide-svelte/icons/wrench";
  let jwt_secret = $state("");
  let generate_string = () => {
    jwt_secret = [...Array(64)]
      .map(() => Math.random().toString(36)[2])
      .join("");
  };
  import { copy } from "svelte-copy";

  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };
</script>

<div class="jwt_wrapper">
  <h1>JWT secret generator</h1>
  <p>
    A JWT (JSON Web Token) Secret Generator is a tool used to create a secure
    secret key for signing JWTs. This secret is critical for ensuring the
    integrity and authenticity of the token, as it is used to verify the payload
    and prevent tampering. When generating a JWT, the secret key should be kept
    private and stored securely.
  </p>
  <button onclick={generate_string}>Generate <Wrench /></button>
  <p class="break-text">
    {jwt_secret}
  </p>
  <button onclick={copy_it} use:copy={jwt_secret}>Copy code</button>
</div>
