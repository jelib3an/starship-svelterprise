<script>
  import { setContext } from 'svelte';
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

  setContext('ss.starfield', {
    width: () => width,
    height: () => height,
  });

  $: width = width > maxWidth ? maxWidth : width;
  $: height = height > maxHeight ? maxHeight : height;

  let starContainerSm;
  let starContainerMed;
  let starContainerLg;

  function animate(event) {
    const warpFactor = event.detail.warpFactor;
    starContainerSm.style.animationDuration = (!warpFactor ? 0 : 50 / warpFactor) + 's';
    starContainerMed.style.animationDuration = (!warpFactor ? 0 : 100 / warpFactor) + 's';
    starContainerLg.style.animationDuration = (!warpFactor ? 0 : 150 / warpFactor) + 's';
  }
</script>

<div class={$$props.class} style="width:{width}px;">
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

<style type="text/scss">
  /* Randomly plot stars on a size double the max width of canvas. This allows the stars to animate left along entire canvas. */
  @function draw-stars($n) {
    $shadows: '#{random(2000)}px #{random(600)}px #FFF';
    @for $i from 2 through $n {
      $shadows: '#{$shadows} , #{random(2000)}px #{random(600)}px #FFF';
    }
    @return unquote($shadows);
  }

  .starfield {
    background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);
    overflow: hidden;
    position: relative;
  }

  .sm-stars,
  .sm-stars::after {
    width: 1px;
    height: 1px;
    background: transparent;
    box-shadow: draw-stars(900);
  }

  .med-stars,
  .med-stars::after {
    width: 2px;
    height: 2px;
    background: transparent;
    box-shadow: draw-stars(300);
  }

  .lg-stars,
  .lg-stars::after {
    width: 3px;
    height: 3px;
    background: transparent;
    box-shadow: draw-stars(120);
  }

  .sm-stars::after,
  .med-stars::after,
  .lg-stars::after {
    content: ' ';
    position: absolute;
    left: 2000px;
  }

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
</style>
