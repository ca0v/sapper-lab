<script>
  import { likes } from "../../data/stores";
</script>

<p>You have {$likes} for this page</p>
<button on:click={() => ($likes = $likes + 1)}>I like it!</button>
