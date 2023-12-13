<script>
  export let website;
  export let layer;

  const faviconAPI =
    "https://t1.gstatic.com/faviconV2?client=SOCIAL&type=FAVICON&fallback_opts=TYPE,SIZE,URL&url=";
</script>

<a class={layer} href={website.slug}>
  <div>
    <img height="60" src="{faviconAPI}{website.homepage}/&size=128" alt="" />
  </div>
  <h2>
    {website.titel}
  </h2>
</a>

<style>
  a.front,
  a {
    position: relative;
    width: 80%;
    aspect-ratio: 2/1.2;
    text-decoration: none;
    color: white;
  }
  a.front {
    width: 100%;
    transition: 0.5s;
  }
  a.front:hover {
    scale: 1.1;
  }
  div {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
    background-color: white;
  }

  img {
    margin: 2rem;
  }

  a:nth-child(1n) {
    margin-top: 9rem;
  }
  a:nth-child(2n) {
    margin-top: 22rem;
  }
  a:nth-child(3n) {
    margin-top: 32rem;
  }
  a:last-of-type {
    margin-top: 0;
  }

  a.front:nth-child(1n) {
    margin-top: 15rem;
  }
  a.front:nth-child(2n) {
    margin-top: 7rem;
  }
  a.front:nth-child(3n) {
    margin-top: 18rem;
  }

  @media only screen and (max-width: 700px) {
    a {
    width: 120%;
    }
  }
</style>
