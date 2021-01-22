<script context="module">
  import { writable } from 'svelte/store';

  export const warpFactor = writable(1);
  export const maxWarpFactor = 10;
</script>

<script>
  import { derived } from 'svelte/store';

  function increaseWarpFactor() {
    if ($warpFactor < maxWarpFactor) {
      warpFactor.update((n) => n + 1);
    }
  }

  function decreaseWarpFactor() {
    if ($warpFactor > 1) {
      warpFactor.update((n) => n - 1);
    }
  }

  const warpIndicator = derived(warpFactor, ($warpFactor) => {
    return $warpFactor >= maxWarpFactor ? 'Maximum Warp' : 'Warp ' + $warpFactor;
  });
</script>

<div>
  <button on:click={ decreaseWarpFactor }>-</button>
  <button on:click={ increaseWarpFactor }>+</button>
  { $warpIndicator }
</div>

<style>
  div {
    margin: 5px auto 5px auto;
    width: 500px;
  }
  button {
    margin-right: 2px;
    width: 30px;
  }
</style>