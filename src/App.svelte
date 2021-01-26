<script>
  import Starfield from './Starfield.svelte';
  import Starship from './Starship.svelte';
</script>

<main>
  <div>
    <p>Click a ship. Use arrow keys to maneuver. Spacebar to fire photon torpedos.</p>
  </div>
  <Starfield width="500" height="250">
    <Starship posX="100" posY="150" />
    <Starship shipClass="galaxy" posX="275" posY="50" />
  </Starfield>
</main>

<style>
  p {
    text-align: center;
    font-size: 12px;
  }
</style>
