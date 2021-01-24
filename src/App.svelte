<script>
  import Starfield from './Starfield.svelte';
  import Starship from './Starship.svelte';
</script>

<main>
  <h3>Demonstrate warp capability</h3>
  <Starfield>
    <Starship />
  </Starfield>
</main>

<style>
  h3 {
    text-align: center;
  }
</style>
