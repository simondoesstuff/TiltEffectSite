<script>
    import {onDestroy, onMount} from "svelte";
    import VanillaTilt from "vanilla-tilt";

    let ele;

    onMount(() => {
        VanillaTilt.init(ele, {
            speed: 1000,
            max: 10,
            perspective: 500,
            scale: 1.2,
            glare: true
        });
    })

    onDestroy(() => {
        ele?.vanillaTilt.destroy();
    })
</script>


<div bind:this={ele} class="titleCard preserve-3d p-3 sm:p-7 sm:px-14" on:click>
  <h1 class="select-none translate-z-20">SIMON WALKER</h1>
</div>


<style>
    .titleCard {
        @apply border-white text-5xl cursor-grab shadow-2xl text-center;
        letter-spacing: 0.5rem;
        text-rendering: geometricPrecision;
        font-family: 'Kanit', sans-serif;
        text-shadow: rgba(0, 0, 0, 0.5) 0.2rem 0.2rem 0.5rem;
    }

    .titleCard:hover {
        @apply border-2;
        background: rgb(0, 120, 164);
        background: linear-gradient(0deg, rgb(0, 120, 164) 0%, rgb(81, 0, 181) 100%);
    }

    .translate-z-20 {
        transform: translateZ(20px);
    }

    .preserve-3d {
        transform-style: preserve-3d;
    }
</style>