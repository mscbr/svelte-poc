<script>
  // import {onMount, onDestroy} from 'svelte';
  import {FeedbackStore} from '../stores';
  import { fade, scale } from 'svelte/transition';
  import FeedbackItem from "./feedback-item.svelte";
  // LONG WAY
  // let feedback = [];

  // const unsubscribe = FeedbackStore.subscribe((data) => feedback = data);

  // onMount(() => {
  //   console.log("list mounted");
  // });

  // onDestroy(() => {
  //   unsubscribe();
  // });
</script>
<!-- subscribes & unsubscribes AUTOMATICALLY -->
{#each $FeedbackStore as fb (fb.id)}
  <div in:scale out:fade="{{ duration: 600}}">
    <FeedbackItem item={fb} />
  </div>
{/each}