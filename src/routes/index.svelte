<script>
    import VanillaTilt from "vanilla-tilt";
    import { fly } from 'svelte/transition';
    import {onDestroy, onMount} from "svelte";

    let tiltElements;

    onMount(() => {
        tiltElements = document.querySelectorAll('.vanillatilt');

        VanillaTilt.init(tiltElements, {
            speed: 500,
            max: 10,
            perspective: 500,
            scale: 1.2,
            glare: true
        });
    })

    onDestroy(() => {
        tiltElements?.forEach(element => {
            element.vanillaTilt.destroy();
        });
    })

    // --------------------------------------------------

    let open = false;
</script>


<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300&display=swap" rel="stylesheet">
</svelte:head>



<main class="globallyCentered">
  <div>

    <div class="preserve-3d titleCard vanillatilt" on:click={() => open = !open}>
      <div class="translate-z-30">
        <h1 class="select-none">SIMON WALKER</h1>
      </div>
    </div>

    {#if open}
<!--      <div class="text-center mt-16">-->
<!--        <div transition:fly={{ y: -100, duration: 2000 }}>simon@simonwakler.tech</div>-->
<!--        <div transition:fly={{ y: -100, duration: 2000 }}>970-581-6899</div>-->
<!--      </div>-->
    {/if}

  </div>
</main>


<style>
  :global(html, body) {
    background-color: black;
    height: 100%;
    @apply text-white;
  }

  .titleCard {
      @apply p-7 px-14 border-white text-5xl cursor-grab;
      letter-spacing: 0.5rem;
      text-rendering: geometricPrecision;
      font-family: 'Kanit', sans-serif;
  }

  .titleCard:hover {
      @apply border-2;
      background: rgb(0, 120, 164);
      background: linear-gradient(0deg, rgb(0, 120, 164) 0%, rgb(81, 0, 181) 100%);
  }

  .globallyCentered {
    @apply grid place-items-center absolute top-0 left-0;
    width: 100%;
    height: 100%;
  }

  .translate-z-30 {
    transform: translateZ(30px);
  }

  .preserve-3d {
    transform-style: preserve-3d;
  }
</style>