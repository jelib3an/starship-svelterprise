<script>
  import { getContext } from 'svelte';

  const { width: canvasWidth, height: canvasHeight } = getContext('ss.starfield');
  const { width: shipWidth, height: shipHeight } = getContext('ss.starship');

  export let posX;
  export let posY;
  export let keydownEvent;

  $: navigate(keydownEvent?.keyCode);

  function navigate(keyCode) {
    let x;
    let y;
    switch (keyCode) {
      case 37: // left
        x = posX - 10;
        break;
      case 38: // up
        y = posY - 10;
        break;
      case 39: // right
        x = posX + 10;
        break;
      case 40: // down
        y = posY + 10;
        break;
      default:
        return;
    }

    if (x > 0 && x < canvasWidth() - shipWidth()) {
      posX = x;
    }

    if (y > 0 && y < canvasHeight() - shipHeight()) {
      posY = y;
    }
  }
</script>
