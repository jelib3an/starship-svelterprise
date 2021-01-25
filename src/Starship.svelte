<script>
  import { getContext } from "svelte";

  /**
   * The starship class. Defaults to "ambassador".
   *
   * @type {"ambassador" | "galaxy"}
   */
  export let shipClass = 'ambassador';
  $: if (!['ambassador', 'galaxy'].includes(shipClass)) {
    shipClass = 'ambassador';
  }

  const shipWidth = 100;
  const shipHeight = 30;

  /**
   * The x position of the starship relative to starfield container.
   *
   * @type {integer}
   */
  export let posX = 0;

  /**
   * The y position of the starship relative to the starfield container.
   *
   * @type {integer}
   */
  export let posY = 0;

  const { width: canvasWidth, height: canvasHeight } = getContext('ss.starfield');

  function navigate(e) {
    let x;
    let y;
    switch (e.keyCode) {
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

    if (x > 0 && x < (canvasWidth() - shipWidth)) {
      posX = x;
    }

    if (y > 0 && y < (canvasHeight() - shipHeight)) {
      posY = y;
    }
  }

</script>

<div style="position:absolute; left:{posX}px; top:{posY}px;" tabIndex="0" on:keydown|preventDefault={navigate}>
  <img src="{shipClass}-class.png" alt="starship" />
</div>
