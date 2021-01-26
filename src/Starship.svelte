<script>
  import { setContext } from "svelte";
  import Navigations from "./Navigations.svelte";

  /**
   * The starship class. Defaults to "ambassador".
   *
   * @type {"ambassador" | "galaxy"}
   */
  export let shipClass = 'ambassador';
  $: if (!['ambassador', 'galaxy'].includes(shipClass)) {
    shipClass = 'ambassador';
  }

  const width = 100;
  const height = 30;

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

  // ensure positions are always integers (need typescript!)
  $: posX = parseInt(posX);
  $: posY = parseInt(posY);

  setContext('ss.starship', {
    posX: () => posX,
    posY: () => posY,
    width: () => width,
    height: () => height,
  });

  let keydownEvent = {};
  function keydown(event) {
    keydownEvent = event;
  }
</script>

<div style="position:absolute; left:{posX}px; top:{posY}px;" tabIndex="0" on:keydown|preventDefault={keydown}>
  <img src="{shipClass}-class.png" alt="starship" />
</div>
<Navigations bind:posX={posX} bind:posY={posY} bind:keydownEvent={keydownEvent} />
