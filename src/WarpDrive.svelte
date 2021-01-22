<script>
  import { warpFactor } from './stores.js';

  function increaseWarpFactor() {
    if ($warpFactor < 10) {
      warpFactor.update((n) => n + 1);
    }
  }

  function decreaseWarpFactor() {
    if ($warpFactor > 1) {
      warpFactor.update((n) => n - 1);
    }
  }
</script>

<div>
  Warp Factor { $warpFactor }
  <button on:click={ increaseWarpFactor }>+</button>
  <button on:click={ decreaseWarpFactor }>-</button>
</div>

<style>
  div {
    margin: 5px auto 5px auto;
    width: 500px;
  }
  button {
    margin-left: 2px;
    width: 30px;
  }
</style>