<script lang="ts">
    let open = false;
</script>

<main>
    <h1 class="text-center p-4">Used javascript + CSS animated the open and close menu button</h1>
    <div class="wrapper">
        <div class:open={open} on:click={() => open = !open} class="btn">
            <div class="burger_3"></div>
        </div>
    </div>
</main>

<style>
    .wrapper {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .btn {
        display: flex;
        justify-content: center; 
        align-items: center;
        border: solid 5px blue;;
        height: 100px;
        width: 100px;
        transition: .5s ease-in-out;
        cursor: pointer;
        box-sizing: content-box;
        padding: 10px;
    }

    .burger_3 {
        position: relative;
        width: 100px;
        height: 15px;
        background-color: blue;
        border-radius: 10px;
        box-shadow: 0 2px 5px rgba(255, 101, 47, .2);
        transition: .5s ease-in-out;
    }

    .burger_3::before, .burger_3::after {
        content: '';
        position: absolute;
        width: 100px;
        height: 15px;
        background-color: blue;
        border-radius: 10px;
        box-shadow: 0 2px 5px rgba(255, 101, 47, .2);
        transition: .5s ease-in-out;
        left: 0;
    }

    .burger_3::before { transform: translateY(-35px); }

    .burger_3::after { transform: translateY(35px); }

    /* ANIMATION */
    .btn.open .burger_3 {
        transform: translateX(-100px);
        background-color: transparent;
        box-shadow: none;
    }
    .btn.open .burger_3::before { transform: rotate(45deg) translate(71px, -71px); }
    .btn.open .burger_3::after { transform: rotate(-45deg) translate(71px, 71px); }
</style>