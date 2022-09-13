<script lang="ts">
  import type { Person } from './CPerson';
  import AddEmployeeForm from './AddEmployeeForm.svelte';
  import EditEmployeeForm from './EditEmployeeForm.svelte';
  let employees: Array<Person> = [];
  let employee: Person;
  
  let edit = false;

  const addEmployee = (event: CustomEvent) => {
    const newEmployee = event.detail as Person;
    employees = [newEmployee, ...employees];
  }

  const deleteEmployee = (id: number) => {
    employees = employees.filter((employee) => employee.id !== id);
  }

  const editEmployee = (id: number) => {
    employee = employees.find((employee) => employee.id === id);
    edit = true;
  }

  const updateEmployee = (event: CustomEvent) => {
    employee = event.detail as Person;
    const updatedEmployee = employees.find((emp) => emp.id === employee.id);
    updatedEmployee.firstName = employee.firstName;
    updatedEmployee.lastName = employee.lastName;
    employees = [...employees];
    edit = false;
  }

</script>

<h1 class="p-4 text-center">Example of CRUD (array data only not persistent)</h1>
<main class="bg-gray-500 p-10 flex justify-center flex-col items-center">
  {#if !edit}
    <AddEmployeeForm on:addEmployee={addEmployee} />
  {:else}
    <EditEmployeeForm on:updateEmployee={updateEmployee} employee={employee} />
  {/if}

  <ul class="w-full">
    {#each employees as employee (employee.id)}
        <li
          on:click={() => editEmployee(employee.id)}
          class="my-2 first:mt-10 last:mb-0 w-full p-5 border border-1 border-green-700 bg-yellow-200"
        >
          <div class="flex justify-end">
            <button
              on:click={() => deleteEmployee(employee.id)}
              class="w-[30px] h-[30px] rounded-full bg-red-700 px-2 pb-1 text-white font-bold">
              x
            </button>
          </div>
          <div>{`${employee.firstName} ${employee.lastName}`}</div>
        </li>
    {/each}
    <!-- <div class="border-4 border-blue-200">hey</div> -->
  </ul>
</main>

<style>
</style>