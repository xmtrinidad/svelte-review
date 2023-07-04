<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  function emitMeme() {
    dispatch('meme', {
      text: 'lol you got meme'
    });
  }
</script>

<button on:click={emitMeme}>Emit Meme</button>