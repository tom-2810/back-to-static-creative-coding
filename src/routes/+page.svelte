<script>
  import { gsap } from "gsap/dist/gsap";
  import { ScrollTrigger } from "gsap/dist/ScrollTrigger";

  import { onMount } from "svelte";

  import Heading from "$lib/components/heading.svelte";
  import Partner from "$lib/components/partner.svelte";
  import SpikePartner from "$lib/components/SpikePartner.svelte";
  export let data;
  gsap.registerPlugin(ScrollTrigger);

  let heading = { titel: "Partners overzicht" };

  // form submit
  let input;
  function submit() {
    let websites = document.querySelectorAll(".website");

    websites.forEach((website) => {
      if (!website.innerText.toUpperCase().includes(input.toUpperCase())) {
        website.classList.add("container-off");
      } else {
        website.classList.remove("container-off");
      }
    });
  }

  onMount(() => {
    let tl = gsap.timeline({
      scrollTrigger: {
        trigger: "ul.bg",
        start: `-20% top`,
        end: `120% bottom`,
        scrub: 1,
        markers: true,
      },
    });
    tl.to("ul.bg", {
      y: 700,
    });
  });
</script>

<Heading {heading} />

<form on:submit|preventDefault={submit}>
  <label for="partner-search">Zoek een partner</label>
  <input
    type="search"
    id="partner-search"
    placeholder="Connexxion"
    bind:value={input}
  />
</form>

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
	height: fit-content;
  }
  /* form */

  form {
    margin: 0 1em;
    margin-bottom: 1em;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    gap: 1em;
    font-weight: 600;
  }

  input {
    padding: 0.5em;
    border: 1px solid var(--c-modal-button);
    background-color: var(--c-container);
    border-radius: 0.25em;
    color: var(--c-white);
    width: 8.5em;
    font-size: 1em;
    font-weight: 600;
    padding-left: 0.75em;
  }
  /* form end */
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
