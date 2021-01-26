<script>
  import { createEventDispatcher } from 'svelte';

  const maxWarpFactor = 10;

  let warpFactor = 0;

  function increaseWarpFactor() {
    if (warpFactor < maxWarpFactor) {
      warpFactor++;
    }
  }

  function decreaseWarpFactor() {
    if (warpFactor > 0) {
      warpFactor--;
    }
  }

  /**
   * @event {{ warpFactor: integer }} change
   */
  const dispatch = createEventDispatcher();
  $: dispatch('change', { warpFactor: warpFactor });

  $: warpIndicator =
    warpFactor >= maxWarpFactor
      ? 'Maximum Warp'
      : 'Warp ' + (warpFactor ? warpFactor : 'Disengaged');
  $: quote = warpFactor >= maxWarpFactor ? "(I'm giving her all she's got, captain!)" : '';
</script>

<div>
  <button on:click={decreaseWarpFactor}>-</button>
  <button on:click={increaseWarpFactor}>+</button>
  <span>{warpIndicator}</span>
  <span class="quote">{quote}</span>
</div>

<style>
  button {
    margin-right: 2px;
    width: 30px;
  }

  span {
    font-size: 12px;
  }

  .quote {
    font-style: italic;
  }
</style>
