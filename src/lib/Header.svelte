<script lang="ts">
    import ToggleMenuButton from "./ToggleMenu/ToggleMenuButton.svelte";
    import Fa from "svelte-fa";
    import { faBars } from "@fortawesome/free-solid-svg-icons";
    export let value: boolean;
    const showHideMenu = () => value = !value;
    const icon_th = 9776;
    const icon_cr = 9886;
    const icon_cl = 9932;
    let icon = icon_th;
    $: { icon = value ? icon_cl : icon_th }
</script>

<div class="header flex items-center bg-gray-400 text-white">
    <!-- <button on:click={showHideMenu} class="mr-5 p-3 hov
       er:bg-gray-500"> -->
            <!-- <Fa class="hover:cursor-pointer h-full w-full" icon={faBars} /> -->
            <!-- <b>{@html `&#${icon};`}</b> -->
        <!-- </button> -->
    <ToggleMenuButton open={value} on:click={showHideMenu} />
    <div class="flex-1 text-right mr-2">Manager</div>
</div>

<style lang="postcss">

</style>