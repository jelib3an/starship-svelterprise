<script>
  import { getContext } from 'svelte';

  export let keydownEvent;
  let photon;

  const {
    posX: starshipPosX,
    posY: starshipPosY,
    width: starshipWidth,
    height: starshipHeight,
  } = getContext('ss.starship');

  const { width: canvasWidth } = getContext('ss.starfield');

  // spacebar
  $: if (keydownEvent?.keyCode === 32) {
    fire();
  }

  function sleep(ms) {
    return new Promise((resolve) => setTimeout(resolve, ms));
  }

  async function fire() {
    let posX = parseInt(starshipPosX() + starshipWidth() / 2);
    let posY = parseInt(starshipPosY() + starshipHeight() / 2);

    const clone = photon.cloneNode();
    photon.parentNode.appendChild(clone);
    clone.style.left = posX + 'px';
    clone.style.top = posY + 'px';

    for (let i = 0; i < canvasWidth(); i++) {
      posX++;
      clone.style.left = posX + 'px';
      await sleep(7);
    }
  }
</script>

<div class="photon" bind:this={photon} />

<style>
  .photon {
    position: absolute;
    top: -10px;
    left: -10px;
    background: rgba(255, 177, 66, 1);
    border-radius: 50%;
    box-shadow: 0 0 0 0 rgba(255, 177, 66, 1);
    height: 6px;
    width: 6px;
    transform: scale(1);
    animation: pulse 1s infinite;
  }

  @keyframes pulse {
    0% {
      transform: scale(0.95);
      box-shadow: 0 0 0 0 rgba(255, 177, 66, 0.7);
    }

    70% {
      transform: scale(1);
      box-shadow: 0 0 0 10px rgba(255, 177, 66, 0);
    }

    100% {
      transform: scale(0.95);
      box-shadow: 0 0 0 0 rgba(255, 177, 66, 0);
    }
  }
</style>
