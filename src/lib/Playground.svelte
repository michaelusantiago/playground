<script>
    let animate = false;
</script>

<style>
    h1 {
        position: relative;
    }
    h1:before {
        content: '';
        position: absolute;
        border: solid 1px blue;
        width: 50px;
    }

    .el {
        background-color: darkslategrey;
        clip-path: polygon(50% 0%, 1% 0, 100% 0);
        transition: clip-path 1s;
        height: 300px;
        width: 300px;
    }

    .anamae {
        clip-path: polygon(50% 0%, 0 100%, 100% 100%);
    }

    .boxy {
        top: 50%;
        left: 50%;
        position: fixed;
        transform: translate(-50%, -50%);
        height: 300px;
        width: 300px;
        background-color: white;
        animation: transform;
        animation-duration: .2s;
        animation-delay: 1s;
        animation-timing-function: linear;
        animation-iteration-count: infinite;
        /* transition-property: all;
        transition-duration:  1s;
        transition-timing-function:  inifinite; */
    }

    @keyframes transform {
        from { transform: rotate(0deg); } 
        to { transform: rotate(180deg); }
    } 
</style>

<div class="bg-yellow-700 grid h-[50vh] place-content-center">
    <div class="bg-green-700 p-20 text-white">
        hello world!
    </div>
    <br />
    <h1>Hello There!</h1>
</div>

<div>
    <label>
        <input type="checkbox" bind:checked={animate}/>
        animate
    </label>
    <div class:anamae={animate} class="el">
    </div>
</div>

<div class="h-[500px] w-[500px]">
    <div class='boxy'></div>
</div>