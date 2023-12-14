<script>
  import { gsap } from "gsap/dist/gsap";
  import { ScrollTrigger } from "gsap/dist/ScrollTrigger";

  import { onMount } from "svelte";

  import Heading from "$lib/components/heading.svelte";
  import Partner from "$lib/components/partner.svelte";
  import SpikePartner from "$lib/components/SpikePartner.svelte";
  import SpikeHeading from "$lib/components/SpikeHeading.svelte";
  export let data;
  gsap.registerPlugin(ScrollTrigger);

  onMount(() => {
    let tl = gsap.timeline({
      scrollTrigger: {
        trigger: "ul.bg",
        start: `-10% top`,
        end: `120% bottom`,
        scrub: 1,
        markers: false,
      },
    });
    tl.to("ul.bg", {
      y: 900,
    });
  });
</script>

<SpikeHeading />

<section>
  <ul>
    {#each data.websites as website}
      <SpikePartner {website} layer="front" />
    {/each}
  </ul>

  <ul class="bg">
    {#each data.websites.reverse() as website}
      <SpikePartner {website} />
    {/each}
  </ul>
</section>

<style>
  section {
    position: relative;
    height: 200vh;
    overflow-y: hidden;
  }

  ul {
    position: absolute;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    column-gap: 5%;
    width: 100%;
    max-width: 80rem;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
  }

  ul.bg {
    top: -15rem;
    column-gap: 3%;
    max-width: 70rem;
    margin: 0 auto;
    z-index: -1;
  }

  @media only screen and (max-width: 700px) {
    ul {
      grid-template-columns: repeat(2, 1fr);
    }
  }
</style>
