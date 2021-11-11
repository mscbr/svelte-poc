<script>
  import FeedbackItem from "./feedback-item.svelte";
  export let feedback = [];

</script>

{#each feedback as fb (fb.id)}
  <FeedbackItem item={fb} on:delete-feedback />
{/each}