<script>
  /**
   * The starship class. Defaults to "ambassador".
   *
   * @type {"ambassador" | "galaxy"}
   */
  export let shipClass;
  $: if (!['ambassador', 'galaxy'].includes(shipClass)) {
    shipClass = 'ambassador';
  }

  const shipWidth = 100;
  const shipHeight = 30;

  let posX = 200;
  let posY = 75;
</script>

<div style="position:relative; left:{posX}px; top:{posY}px;">
  <img src="{shipClass}-class.png" alt="starship" />
</div>
