<main>
    <h1 class="text-center p-4">Pure CSS animated the open and close menu button. Just rotated the whole element</h1>
    <div class="wrapper">
        <label class="btn">
            <input style:display="none" type="checkbox"/>
            <div class="greater-arrow"></div>
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
        background-color: violet;
        display: flex;
        justify-content: center; 
        align-items: center;
        /* border: solid 5px blue;; */
        height: 100px;
        width: 100px;
        transition: .5s ease-in-out;
        cursor: pointer;
        box-sizing: content-box;
        padding: 10px;
    }

    .greater-arrow {
        position: relative;
        float: left;
        padding: 0 18px;
        transform: rotate(0deg);
        transition: transform linear 0.2s;
    }
    .greater-arrow:before,
    .greater-arrow:after {
        content: '';
        left: -0%;
        top: 50%;
        border: solid transparent;
        height: 0;
        width: 0;
        position: absolute;
    }
    .greater-arrow:after {
        border-left-color: violet;
        border-width: 30px;
        margin-top: -30px;
    }
    .greater-arrow:before {
        /* border-color: rgba(194, 225, 245, 0); */
        border-left-color: #F39200;
        border-width: 34px;
        margin-top: -34px;
    }

    .btn input[type="checkbox"]:checked ~ .greater-arrow {
        transform: rotate(90deg);
        transition: transform linear 0.2s;
    }

</style>