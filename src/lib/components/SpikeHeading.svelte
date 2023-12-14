<script>
  import Tower from "$lib/components/tower.svelte";

</script>

<div>

  <Tower />
  <span>Vervoerregio Partners</span>
</div>
<style>
  div {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    max-width: 70rem;
    margin: 0 auto;
    margin-bottom: 20rem;
  }

  span {
    font-size: clamp(3rem, 6vw, 6rem);
    width: min-content;
    font-weight: 800;
  }

  @media only screen and (max-width: 900px) {
    div {
      flex-direction: column;
      gap: 10rem;
    }
  }
</style>