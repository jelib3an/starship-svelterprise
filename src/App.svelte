<script>
  import Starfield from './Starfield.svelte';
  import Starship from './Starship.svelte';
</script>

<main>
  <div>
    <p>Click a ship.</p>
    <p>Use arrow keys to maneuver.</p>
  </div>
  <Starfield width="500" height="250">
    <Starship posX="100" posY="150" />
    <Starship shipClass="galaxy" posX="275" posY="50" />
  </Starfield>
</main>

<style>
  div {
    text-align: center;
    font-size: 12px;
  }
</style>
