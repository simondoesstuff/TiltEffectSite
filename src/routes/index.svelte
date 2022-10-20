<script>
    import {fly, fade} from 'svelte/transition';
    import TitleCard3D from "../components/TitleCard3D.svelte";

    let open = false;
</script>


<main class="globallyCentered">
    <div class="titleCard"
         class:float={open}>
      <TitleCard3D on:click={() => open = !open}/>
    </div>
</main>

<!--   Software dev details     -->
{#if open}
  <div class="globallyCentered text-center -z-10">
    <div class="relative top-10">
      <div class="shadow-2xl font-bold p-2" transition:fly={{ y: -30, duration: 800, delay: 0 }}>Software Developer</div>
      <div class="shadow-2xl extraLetterSpacing p-2" transition:fly={{ y: -30, duration: 800, delay: 250 }}>simon@simonwalker.tech</div>
      <div class="shadow-2xl extraLetterSpacing p-2" transition:fly={{ y: -30, duration: 800, delay: 500 }}>970 581 6899</div>
    </div>
  </div>
{/if}


<!--    Jumpscare photo   -->
<!-- {#if open}
  <div class="globallyCentered -z-20 w-full transparencyGradient">
    <img
        src="./personalPicture.png"
        class="relative -top-28"
        transition:fade={{ duration: 1500, delay: 1000 }}
        alt=""
    >
  </div>
{/if} -->


<style>
    :global(body) {
        height: 100%;
    }

    .transparencyGradient {
        mask-image: linear-gradient(to bottom, rgba(0, 0, 0, 1) 0%, transparent 65%);
    }

    .titleCard {
        @apply transition-transform;
        transition-duration: 1000ms;
    }

    .titleCard.float {
        position: relative;
        transform: translateY(-7rem);
    }

    .globallyCentered {
        @apply grid place-items-center absolute top-0 left-0;
        width: 100%;
        height: 100%;
    }

    .extraLetterSpacing {
        @apply p-2;
        letter-spacing: 0.3rem;
    }
</style>
