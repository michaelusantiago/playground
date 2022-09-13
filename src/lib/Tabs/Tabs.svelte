<script lang='ts'>
    let numbers = new Array(50).fill('hello', 0, 50)
    let current_tab = 1
</script>

<style>
    .tabs-body {
        --tabs-head-height: 2.5em;
        background-color: peru;
        overflow: auto;
    }

    .tabs-head {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .tabs-head > li {
        padding: 5px 20px;
        margin: 0 2px;
        height: var(--tabs-head-height);
        background-color: blueviolet;
    }

    .tab-content {
        background-color: yellowgreen;
        border-top: solid 1px blueviolet;
        padding: 5px;
        height: calc(100vh - 7.5em);
        overflow: auto;
    }
</style>

<div class="tabs-body">
    <div class="flex justify-end items-center">
        <button class="m-2">&#9587</button>
    </div>
    <ul class="tabs-head">
        <li><button on:click={() => current_tab = 1}>Client's Info</button></li>
        <li><button on:click={() => current_tab = 2}>Subscription</button></li>
    </ul>
    {#if current_tab === 1}
        <div class="tab-content">
            {#each numbers as num}
                <div>{num}</div>
            {/each}
        </div>
    {:else}
        <div class="tab-content">
            Tab2 Content
        </div>
    {/if}
</div>