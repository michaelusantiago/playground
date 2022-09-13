<script lang="ts">
    import { Person } from "./CPerson"
    import { createEventDispatcher } from "svelte";
    export let employee: Person = new Person('', '');

    let dispatcher = createEventDispatcher();

    const updateEmployee = (event: Event) => {
        dispatcher("updateEmployee", employee);
    }

</script>

<div>
    <input readonly={true} class="m-2 px-3 py-1 border-2 border-black read-only:bg-gray-400" type="text" bind:value={employee.id} />
    <form on:submit|preventDefault={updateEmployee}>
        <input class="m-2 px-3 py-1 border-2 border-black" type="text" bind:value={employee.firstName} />
        <input class="m-2 px-3 py-1 border-2 border-black" type="text" bind:value={employee.lastName} />
        <button class="border rounded-lg border-blue-800 bg-blue-300 px-5 py-2">Update</button>
    </form>
</div>