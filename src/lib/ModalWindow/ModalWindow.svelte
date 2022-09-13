<script>
    import ModalWindow1 from './ModalWindow1.svelte'
    let show_mw = false;
</script>

<style>
    .show-mw-btn {
        background-color: #2255AA;
        padding: 2em 5em;
        text-transform: uppercase;
        color: white;
    }

    /* .wrapper {
        display: grid;
        height: 90vh;
        place-content: center;
        background-color: orange;
    } */
</style>

<div class="bg-orange-500 grid h-[90vh] place-content-center">
<!-- <div class="wrapper"> -->
    <button on:click={() => show_mw = !show_mw} class="show-mw-btn">Open a modal window</button>
</div>

{#if show_mw}
    <ModalWindow1 on:close={() => show_mw = false} --mw-height=200px --mw-width=400px>
        <div>Something went wrong, please check your internet connection!</div>
        <button on:click={() => show_mw = false} class="px-7 py-2 bg-red-500 text-white">close</button>
    </ModalWindow1>
{/if}