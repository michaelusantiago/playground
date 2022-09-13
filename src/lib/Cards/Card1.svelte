<style>
    .container {
        display: grid;
        height: 100%;
        width: 100%; 
        place-content: center;
    }

    .card {
        position: relative;
        height: 300px;
        width: 400px;
        border: solid 1px darkgray;
        background-color: rgb(57, 145, 223);
        border-radius: 10px;
        box-sizing: border-box;
        padding: 5px;
        padding-top: 37px;
    }

    .close-btn {
        position: absolute;
        top: 5px;
        right: 7px;
        border-radius: 50px;
        padding: 3px 7px;
        font-weight: bold;
        text-align: center;
        color: rgb(142, 178, 209);
        transition: color .5s;
        background-color: green;
        z-index: 1;
    }
    .close-btn:hover { color: white; }

    .content {
        position: relative;
        background-color: brown;
        height: 100%;
        z-index: 0;
    }
</style>

<div class="container">
    <h1 class="text-center my-5">It uses position relative to achieve it</h1>
    <div class="card">
        <button class="close-btn">&#x26CC;</button>
        <div class="content">hello</div>
    </div>
</div>