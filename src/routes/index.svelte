<script>
    import {fly} from 'svelte/transition';
    import TitleCard3D from "../components/TitleCard3D.svelte";

    // --------------------------------------------------

    let open = false;
</script>


<main class="globallyCentered">
  <div>

    <TitleCard3D on:click={() => open = !open}/>

    {#if open}
      <div class="text-center mt-5">
        <div class="contactDetail" transition:fly={{ y: -50, duration: 1000 }}>simon@simonwalker.tech</div>
        <div class="contactDetail" transition:fly={{ y: -50, duration: 1000, delay: 200 }}>970  581  6899</div>
      </div>
    {/if}

  </div>
</main>


<style>
    :global(html, body) {
        background-color: black;
        height: 100%;
        @apply text-white;
    }

    .globallyCentered {
        @apply grid place-items-center absolute top-0 left-0;
        width: 100%;
        height: 100%;
    }

    .contactDetail {
        @apply mb-5;
        letter-spacing: 0.5rem;
    }
</style>