<script lang="ts">
    let plan:number = 1
</script>

<style lang="postcss">
    main input[type="radio"] { display: none; }

    main span {
        background-color: darkkhaki;
        padding: 20px;
        cursor: pointer;
    }

    main input[type='radio']:checked ~ span {
        background-color: blue;
    }
</style>

<main class="flex justify-between p-10">
    <label>
        <input type="radio" bind:group={plan} value={1}/>
        <span>Plan 1</span>
    </label>
    <label>
        <input type="radio" bind:group={plan} value={2}/>
        <span>Plan 2</span>
    </label>
    <label>
        <input type="radio" bind:group={plan} value={3}/>
        <span>Plan 3</span>
    </label>
</main>