<main>
    <h1 class="text-center p-4">Pure CSS animated the open and close menu button (no flying stick)</h1>
    <div class="wrapper">
        <label class="btn">
            <input style:display="none" type="checkbox"/>
            <div class="burger_3"></div>
        </label>
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
        --deg: 45deg;
        position: relative;
        width: 100px;
        height: 15px;
        background-color: blue;
        border-radius: 10px;
        box-shadow: 0 2px 5px rgba(255, 101, 47, .2);
        transition: .5s ease-in-out;
        cursor: pointer;
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

    /* Animation */
    .btn input[type=checkbox]:checked ~ .burger_3 {
        background-color: transparent;
        box-shadow: none;
    }
    .btn input[type=checkbox]:checked ~ .burger_3::before { transform: rotate(var(--deg)); }
    .btn input[type=checkbox]:checked ~ .burger_3::after { transform: rotate(calc(-1 * var(--deg))); }
</style>