<script lang="ts">
    import { Person } from "./CPerson"
    import { createEventDispatcher } from "svelte";

    let dispatcher = createEventDispatcher();

    const employee: Person = {firstName: '', lastName: '', id: 0};

    const addEmployee = (event: Event) => {
        let newEmployee: Person = new Person(employee.firstName, employee.lastName);
        newEmployee.id = new Date().getTime();

        dispatcher("addEmployee", newEmployee);
    }

    const handleInput = (e: Event) => { }

</script>

<style lang="postcss"></style>

<form on:submit|preventDefault={addEmployee}>
    <input class="m-2 px-3 py-1 border-2 border-black" type="text" bind:value={employee.firstName} />
    <input class="m-2 px-3 py-1 border-2 border-black" type="text" bind:value={employee.lastName} />
    <button class="border rounded-lg border-blue-800 bg-blue-300 px-5 py-2">Add</button>
</form>
