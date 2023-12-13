<script>
  export let heading;
</script>

<div href="#contact" class="banner">
  <div class="banner-content">
    {heading.titel}
    {heading.titel}
  </div>
  <div class="banner-content">
    {heading.titel}
    {heading.titel}
  </div>
</div>

<style>
  .banner {
    width: 240%;
    background-color: white;
    font-size: 4rem;
    flex-shrink: 0;
    display: flex;
    overflow: hidden;
    gap: 0.5rem;
    z-index: 1;
  }
  .banner-content {
    display: flex;
    flex-direction: row;
    flex-shrink: 0;
    animation: scroll 10s linear infinite;
    text-transform: uppercase;
    color: black;
  }

  @keyframes scroll {
    from {
      transform: translateX(0);
    }
    to {
      transform: translateX(calc(-100% - 1rem));
    }
  }
</style>
