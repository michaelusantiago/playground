<style>
    .container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    .card {
        display: flex;
        flex-direction: column;
        height: 300px;
        width: 400px;
        border: solid 1px darkgray;
        background-color: rgb(57, 145, 223);
        border-radius: 10px;
        box-sizing: border-box;
        /* padding: 0 5px 5px 5px; */
    }

    .close-btn {
        background-color: green;
        align-self: flex-end;
        border-radius: 50px;
        padding: 3px 7px;
        margin-top: 5px ;
        margin-right: 5px ;
        font-weight: bold;
        color: rgb(142, 178, 209);
        transition: color .5s;
    }

    .close-btn:hover { color: white; }

    .content {
        background-color: rgba(111, 124, 117, 0.76);
        height: 100%;
        margin: 2px 5px 5px 5px;
    }

</style>

<div class="container">
    <h1 class="text-center my-5">It uses flexbox to achieve positioning, etc..</h1>
    <div class="card">
        <button class="close-btn">&#x26CC;</button>
        <div class="content">hello world</div>
    </div>
</div>