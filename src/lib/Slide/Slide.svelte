<script lang="ts">
    import Slide1 from './Slide1.svelte'
    import Slide2 from './Slide2.svelte'
    let arr = Array(100).fill("hello world", 0, 100)
    let slide_it = false
</script>

<style>
    .slide-body {
        --right-x: 0;
        --left-x: 0;
        display: flex;
        height: calc(100vh - 2em);
    }

    .left-wrapper {
        display: flex;
        flex-direction: column;
        position: relative;
        min-width: 100%;
        left: var(--left-x);
        height: calc(100vh - 3.5em);
        transition: left .5s;
    }
    .left {
        background-color: burlywood;
        /* position: relative; */
        min-width: 100%;
        /* height: calc(100vh - 4.5em);
        left: var(--left-x);
        transition: left .5s; */
    }
    .right {
        display: grid;
        place-content: center;
        background-color: crimson;
        height: calc(100vh - 2.5em);
        position: relative;
        min-width: 100%;
        left: var(--right-x);
        transition: left .5s;
    }
    .show-right {
        --left-x: -100%;
        --right-x: -100%;
    }

</style>

<div class="slide-body bg-blue-500">
    <div class:show-right={slide_it} class='left-wrapper overflow-y-auto'>
        <div class="flex flex-col left overflow-y-auto">
            {#each arr as item}
                <button on:click={() => slide_it = !slide_it}>{item}</button>
            {/each}
        </div>
        <div>hello there footer</div>
    </div>
    <div class:show-right={slide_it} class="right">
        <Slide1 />
        <Slide2 />
        <button on:click={() => slide_it = !slide_it} class="px-7 py-2 bg-green-400">back</button>
    </div>
</div>