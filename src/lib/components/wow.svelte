<script>
  import wowCloud from "$lib/assets/wow-cloud.png";
  import wowSound from '$lib/assets/wow.mp3'

  import { gsap } from "gsap/dist/gsap";
  import { onMount } from "svelte";

  onMount(() => {
    let wow = new Audio();

    wow.src = wowSound

    gsap.to(".page-transition img", {
      opacity: 0,
      duration: 0.8,
      scale: 0,
      onComplete: () => {
        gsap.set(".page-transition", { display: "none" });
      },
    });

    gsap.to(".page-transition .bg", {
      opacity: 0,
      duration: 0.8,
    });

    document.querySelectorAll("a").forEach((link) => {
      link.addEventListener("click", function (e) {
        e.preventDefault();
        let destination = link.href;

        wow.play()

        gsap.set(".page-transition", { display: "flex" });
        gsap.fromTo(
          ".page-transition img",
          {
            opacity: 0,
            scale: 0,
          },
          {
            opacity: 1,
            duration: 1,
            scale: 1,
            onComplete: () => {
              window.location = destination;
            },
          }
        );

        gsap.fromTo(
          ".page-transition .bg",
          {
            opacity: 0,
          },
          {
            opacity: 1,
            duration: 0.5,
          }
        );
      });
    });
  });
</script>

<div class="page-transition">
  <img src={wowCloud} alt="" />
  <div class="bg" />
</div>

<style>
  .page-transition {
    display: none;
  }
  div {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    pointer-events: none;
    z-index: 1;
  }

  .bg {
    width: 100%;
    height: 100%;
    background: repeating-conic-gradient(hotpink 0 10deg, magenta 0 20deg);
  }

  img {
    width: 20rem;
    z-index: 2;
  }
</style>
