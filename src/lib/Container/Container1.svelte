<script lang="ts">
    import GTToggleButton from "../ToggleMenu/GTToggleButton.svelte";

    export let header_title: string

    export let hd_bg_color = "lightgreen"
    export let hd_text_color = "white"
    export let hd_border_color = "blue"
    export let hd_icon_color = "black"

    let open = true;
</script>

<style lang="postcss">
    :root {
        /* defaults */
        --border-color: blue;
        --border-size: 1px;
        --header-bg-color: lightseagreen;
        --header-text-color: white;
    }

    main { border: solid var(--border-size) var(--border-color); }

    .header input[type="checkbox"] { display: none; }

    .header {
        display: flex;
        align-items: center;
        justify-content: space-between;
        background-color: var(--header-bg-color);
        color: var(--header-text-color);
        padding: 15px;
        cursor: pointer;
    }

    .header span {
        display: flex;
        justify-content: center;
        align-items: center;
        transform: rotate(0deg);
        transition: transform linear 0.2s;
    }

    .container {
        height: 150px;
        overflow: hidden;
        transition: height linear 0.2s;
    }

    .header input[type="checkbox"]:checked ~ span {
        transform: rotate(90deg);
        transition: transform linear 0.2s;
    }

    .hide-container {
        height: 0;
        transition: height linear 0.2s;
    }
</style>

<main style:border-color={hd_border_color}>
    <label class="header"
        style:background-color={hd_bg_color}
        style:color={hd_text_color}>
        <input type="checkbox" bind:checked={open}/>
        {header_title}
        <span><GTToggleButton --fill-color={hd_bg_color} --icon-color={hd_icon_color} /></span>
    </label>
    <div class:hide-container={!open} class="container">
        <slot/>
    </div>
</main>