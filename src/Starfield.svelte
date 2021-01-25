<script>
  import { onMount } from 'svelte';
  import WarpControls from './WarpControls.svelte';

  const maxWidth = 1000;
  const maxHeight = 600;

  /**
   * The width of the starfield in pixels.
   *
   * @type {integer}
   */
  export let width = 500;

  /**
   * The height of the starfield in pixels.
   *
   * @type {integer}
   */
  export let height = 200;

  $: width = width > maxWidth ? maxWidth : width;
  $: height = height > maxHeight ? maxHeight : height;

  /**
   * Randomly plot stars on the canvas.
   *
   * @param {integer} n - The number of stars to plot per square pixel
   * @returns {string} The box-shadow css
   */
  function drawStars(n) {
    const shadows = [];
    for (let i = 0; i < n; i++) {
      // randomly plot stars on a size double the max width of canvas
      // this allows the stars to animate left along entire canvas
      const x = Math.floor(Math.random() * maxWidth * 2);
      const y = Math.floor(Math.random() * maxHeight);
      shadows.push(x + 'px ' + y + 'px #FFF');
    }
    return shadows.join(',');
  }

  let starContainerSm;
  let starContainerMed;
  let starContainerLg;

  function animate(event) {
    starContainerSm.style.animationDuration =
      (!event.detail.warpFactor ? 0 : 50 / event.detail.warpFactor) + 's';
    starContainerMed.style.animationDuration =
      (!event.detail.warpFactor ? 0 : 100 / event.detail.warpFactor) + 's';
    starContainerLg.style.animationDuration =
      (!event.detail.warpFactor ? 0 : 150 / event.detail.warpFactor) + 's';
  }
  onMount(() => {
    starContainerSm.style.boxShadow = drawStars(900);
    starContainerMed.style.boxShadow = drawStars(300);
    starContainerLg.style.boxShadow = drawStars(120);
  });
</script>

<div class="container" style="width:{width}px;">
  {#if $$slots.default}
    <WarpControls on:change={animate} />
  {/if}
  <div class="starfield" style="width:{width}px; height:{height}px;">
    <div class="sm-stars" bind:this={starContainerSm} />
    <div class="med-stars" bind:this={starContainerMed} />
    <div class="lg-stars" bind:this={starContainerLg} />
    <slot />
  </div>
</div>

<style>
  .container {
    margin: 5px auto 5px auto;
  }

  .starfield {
    background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);
    overflow: hidden;
    outline: none;
  }

  .sm-stars,
  .sm-stars::after {
    width: 1px;
    height: 1px;
    background: transparent;
  }
  .med-stars,
  .med-stars::after {
    width: 2px;
    height: 2px;
    background: transparent;
  }
  .lg-stars,
  .lg-stars::after {
    width: 3px;
    height: 3px;
    background: transparent;
  }

  /* Animate the stars towards the left. When complete, reset positions 2000px to the right. This has to match max canvas width. */
  @keyframes moveLeft {
    from {
      transform: translateX(0px);
    }
    to {
      transform: translateX(-2000px);
    }
  }

  .sm-stars,
  .med-stars,
  .lg-stars {
    animation: moveLeft linear infinite;
  }

  .sm-stars:after,
  .med-stars:after,
  .lg-stars:after {
    content: ' ';
    position: absolute;
    left: 2000px;
  }
</style>
