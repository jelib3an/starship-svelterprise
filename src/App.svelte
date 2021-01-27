<script>
  import Starfield from './Starfield.svelte';
  import Starship from './Starship.svelte';
</script>

<main>
  <div>
    <h3>One ship</h3>
    <p>Click ship. Use arrow keys to maneuver. Spacebar to fire photon torpedos.</p>
  </div>
  <Starfield class="center" width="500" height="250">
    <Starship posX="200" posY="120" />
  </Starfield>

  <div>
    <h3>Two ships</h3>
    <p>Click a ship. Use arrow keys to maneuver. Spacebar to fire photon torpedos.</p>
  </div>
  <Starfield class="center" width="500" height="250">
    <Starship posX="100" posY="150" />
    <Starship shipClass="galaxy" posX="275" posY="50" />
  </Starfield>

  <div>
    <h3>Nothing to see here. Just some stars..</h3>
  </div>
  <Starfield class="center" width="500" height="250" />
</main>

<style>
  h3 {
    text-align: center;
  }

  p {
    text-align: center;
    font-size: 12px;
  }

  :global(.center) {
    margin: 5px auto 5px auto;
  }
</style>
