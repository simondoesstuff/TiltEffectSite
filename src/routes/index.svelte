<script>
    import {fly} from 'svelte/transition';
    import TitleCard3D from "../components/TitleCard3D.svelte";

    // --------------------------------------------------

    let open = false;
</script>


<main class="globallyCentered">
    <div class="titleCard"
         class:float={open}>
      <TitleCard3D on:click={() => open = !open}/>
    </div>
</main>

{#if open}
  <div class="globallyCentered text-center -z-10">
    <div class="relative top-10">
      <div class="font-bold p-2" transition:fly={{ y: -30, duration: 800, delay: 0 }}>Software Developer</div>
      <div class="extraLetterSpacing p-2" transition:fly={{ y: -30, duration: 800, delay: 250 }}>simon@simonwalker.tech</div>
      <div class="extraLetterSpacing p-2" transition:fly={{ y: -30, duration: 800, delay: 500 }}>970 581 6899</div>
    </div>
  </div>
{/if}


<style>
    :global(body) {
        height: 100%;
    }

    .titleCard {
        @apply transition-transform;
        transition-duration: 1000ms;
    }

    .titleCard.float {
        position: relative;
        transform: translateY(-6rem);
    }

    .globallyCentered {
        @apply grid place-items-center absolute top-0 left-0;
        width: 100%;
        height: 100%;
    }

    .extraLetterSpacing {
        @apply p-2;
        letter-spacing: 0.5rem;
    }
</style>