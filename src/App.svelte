<script>
  import StarshipSvelterprise from "./StarshipSvelterprise.svelte";
  import WarpDrive from "./WarpDrive.svelte";
</script>

<main>
  <h3>Demonstrate warp capability</h3>
  <WarpDrive />
  <StarshipSvelterprise />

  <hr />

  <h3>Demonstrate changing the ship class and quote using props and slots</h3>
  <StarshipSvelterprise shipClass={"galaxy"}>
    <p>Take us out, Mr. Sulu.</p>
  </StarshipSvelterprise>
</main>

<style>
  h3 {
    text-align: center;
  }
</style>