<!-- <script lang="ts">
  interface Task {
    id: number;
    text: string;
    completed: boolean;
  }

  let tasks: Task[] = [];
  let newTask: string = "";

  function addTask() {
    if (newTask.trim() !== "") {
      tasks = [
        ...tasks,
        { id: tasks.length + 1, text: newTask.trim(), completed: false },
      ];
      newTask = "";
    }
  }

  function removeTask(id: number) {
    tasks = tasks.filter((task) => task.id !== id);
    tasks = tasks.map((task, index) => ({ ...task, id: index + 1 }));
  }

  function toggleCompleted(id: number) {
    tasks = tasks.map((task) => {
      if (task.id === id) {
        return { ...task, completed: !task.completed };
      }
      return task;
    });
  }
</script>

<div class="flex items-center justify-center mt-20">
  <div>
    <h1 class="text-center text-2xl font-semibold mb-4">To-Do List</h1>
    <div class="flex mb-4">
      <input
        type="text"
        class="flex-grow border-2 border-gray-300 rounded-lg px-4 py-2 mr-2 focus:outline-none focus:border-blue-500"
        bind:value={newTask}
        placeholder="What's on your mind?"
      />
      <button
        class="bg-blue-500 text-white px-4 py-2 rounded-lg hover:bg-blue-600 focus:outline-none focus:bg-blue-600"
        on:click={addTask}>Add Task</button
      >
    </div>

    <ul>
      {#each tasks as task (task.id)}
        <li
          class="flex items-center justify-between mb-2 p-4"
          class:line-through={task.completed}
        >
          <span class="text-lg">{task.id}: {task.text}</span>
          <div>
            <button
              class="text-blue-500 mr-2 hover:text-blue-600 focus:outline-none focus:text-blue-600"
              on:click={() => toggleCompleted(task.id)}
              >{task.completed ? "Undo" : "Completed"}</button
            >
            <button
              class="text-red-500 hover:text-red-600 focus:outline-none focus:text-red-600"
              on:click={() => removeTask(task.id)}>Remove</button
            >
          </div>
        </li>
      {/each}
    </ul>
  </div>
</div> -->

<!-- <script lang="ts">
  let price: string = "";
  let currency: string = "USD";
  let showError: boolean = false;
  let inputAttempted: boolean = false;
  let inputEnabled: boolean = true; // Add a variable to track if the input is enabled or disabled

  function handlePriceInput(event: Event) {
    if (!inputEnabled) return; // Exit function if input is disabled
    const inputElement = event.target as HTMLInputElement;
    price = inputElement.value;
    showError =
      price.trim() !== "" &&
      (isNaN(parseFloat(price)) || parseFloat(price) < 0);
    inputAttempted = price.trim() !== ""; // Set inputAttempted to true when there is any input
  }

  function handleCurrencyChange(event: Event) {
    const selectElement = event.target as HTMLSelectElement;
    currency = selectElement.value;
  }

  function toggleInput() {
    inputEnabled = !inputEnabled; // Toggle inputEnabled variable
    if (!inputEnabled) {
      // If input is disabled, clear price and reset error states
      price = "";
      showError = false;
      inputAttempted = false;
    }
  }
</script>

<div class="flex flex-col ml-10 mt-10 h-full">
  <label for="price" class="block text-sm font-medium leading-6 text-gray-900">
    Price
  </label>
  <div class="relative mt-2 rounded-md shadow-sm w-80 flex">
    <div
      class="pointer-events-none absolute inset-y-0 left-0 flex items-center pl-3"
    >
      <span class="text-gray-500 sm:text-sm">$</span>
    </div>
    <input
      type="text"
      name="price"
      id="price"
      bind:value={price}
      on:input={handlePriceInput}
      class="block w-full rounded-lg border-0 py-1.5 pl-7 pr-20 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6 {showError
        ? 'border-red-500 ring-red-500'
        : 'border-gray-300'}"
      placeholder="0.00"
      disabled={!inputEnabled}
    />

    <select
      id="currency"
      name="currency"
      bind:value={currency}
      on:change={handleCurrencyChange}
      class="h-full rounded-md border-0 bg-transparent py-0 pl-2 pr-7 text-gray-500 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm absolute right-0 top-1/2 transform -translate-y-1/2"
      disabled={!inputEnabled}
    >
      <option value="USD">USD</option>
      <option value="CAD">CAD</option>
      <option value="EUR">EUR</option>
    </select>
  </div>
  {#if showError && inputAttempted}
    <p class="mt-1 text-sm text-red-500">Invalid input :(</p>
    <p class="mt-1 text-sm text-gray-500">Please enter a valid input</p>
  {/if}

  
  <button
    class="mt-2 px-4 py-2 bg-blue-500 text-white rounded-md hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-500 self-start"
    on:click={toggleInput}
  >
    {inputEnabled ? "Disable Input" : "Enable Input"}
  </button>
</div> -->
