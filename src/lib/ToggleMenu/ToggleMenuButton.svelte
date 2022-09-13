<script lang="ts">
    export let open: boolean;
</script>

<div class="wrapper bg-gray-700">
    <button class:open={open} on:click class="btn">
        <div class="burger_3"></div>
    </button>
</div>

<style>
    .wrapper {
        --width: 24px;
        --height: 24px;
        --burger-height: 3px;
        --slide-left-x: -10px;
        --trans-x: 7px;
        --bar-space: 8px;
        --angle: 45deg;
        --bar-color: #FFF;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .btn {
        display: flex;
        justify-content: center; 
        align-items: center;
        width: var(--width);
        height: var(--height);
        transition: .5s ease-in-out;
        cursor: pointer;
        box-sizing: content-box;
        padding: 8px;
    }

    .burger_3 {
        position: relative;
        width: var(--width);
        height: var(--burger-height);
        background-color: var(--bar-color);
        border-radius: 10px;
        box-shadow: 0 2px 5px rgba(255, 101, 47, .2);
        transition: .5s ease-in-out;
    }

    .burger_3::before, .burger_3::after {
        content: '';
        position: absolute;
        width: var(--width);
        height: var(--burger-height);
        background-color: var(--bar-color);
        border-radius: 10px;
        box-shadow: 0 2px 5px rgba(255, 101, 47, .2);
        transition: .5s ease-in-out;
        left: 0;
    }

    .burger_3::before { transform: translateY(calc(var(--bar-space) * -1)); }
    .burger_3::after { transform: translateY(var(--bar-space)); }

    /* ANIMATION */
    .btn.open .burger_3 {
        transform: translateX(var(--slide-left-x));
        background-color: transparent;
        box-shadow: none;
    }
    .btn.open .burger_3::before { transform: rotate(45deg) translate(var(--trans-x), calc(var(--trans-x) * -1)); }
    .btn.open .burger_3::after { transform: rotate(-45deg) translate(var(--trans-x), var(--trans-x)); }
</style>