<script>
  import { Highlight } from "svelte-highlight";
  import { javascript } from "svelte-highlight/languages";
  let code = $state(`
const productSchema = new mongoose.Schema({
  title: {
    type: String,
    required: true,
    default: 'Apple'
  },
  description: {
    type: String,
    required: true,
  },
  imageUrl: {
    type: String,
    required: true
  },
});`);
</script>
