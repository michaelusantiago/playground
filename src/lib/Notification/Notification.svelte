<script lang="ts">
    import Notification1 from "./Notification1.svelte";

    let show = false;

    const onShowNotification = async () => {
        show = true
        const timeout = setTimeout(() => show = false, 3000)
    }
</script>

<style lang="postcss">
    .main {
        display: grid;
        place-content: center;
        height: 90vh;
    }
    button {
        background-color: rgb(169, 169, 169);
        padding: 10px 20px;
    }
    button:hover { background-color: rgb(189, 189, 189); }
    button:active { background-color: rgb(169, 169, 169); }
</style>

<div class="main">
    {#if show}
        <Notification1 success={true}>
            <div slot="message">Password was reset successfully</div>
        </Notification1>
    {/if}
    <button on:click={onShowNotification}>Show notification</button>
</div>