<script>
    import VanillaTilt from "vanilla-tilt";
    import {onDestroy, onMount} from "svelte";

    let tiltElements;

    onMount(() => {
        tiltElements = document.querySelectorAll('.vanillatilt');

        VanillaTilt.init(tiltElements, {
            max: 25,
            speed: 400,
            scale: 2,
            glare: true
        });
    })

    onDestroy(() => {
        tiltElements?.forEach(element => {
            element.vanillaTilt.destroy();
        });
    })
</script>



<main class="globallyCentered">
    <div class="preserve-3d titleCard vanillatilt">
      <div class="translate-z-20">
        <h1>SIMON WALKER</h1>
      </div>
    </div>
</main>


<style>
  :global(html, body) {
    background-color: black;
    height: 100%;
    @apply text-white;
  }

  .titleCard {
      @apply p-5 border-white;
  }

  .titleCard:hover {
      @apply border-2;
      background: rgb(255,222,137);
      background: linear-gradient(90deg, rgba(255,222,137,1) 0%, rgba(115,0,255,1) 100%);
  }

  .globallyCentered {
    @apply grid place-items-center absolute top-0 left-0;
    width: 100%;
    height: 100%;
  }

  .translate-z-20 {
    transform: translateZ(20px);
  }

  .preserve-3d {
    transform-style: preserve-3d;
  }
</style>