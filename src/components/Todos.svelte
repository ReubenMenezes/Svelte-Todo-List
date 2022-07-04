<script>
    let todoList = []
    let newTodo;
    function addTodoItem(){
        todoList = [...todoList,{task:newTodo}]
    }
</script>

<style>
    @import "../global.css";
</style>

<!-- Todos.svelte -->
<div class="todoapp stack-large">
    <!-- NewTodo -->
    <form on:submit|preventDefault={addTodoItem}>
      <h2 class="label-wrapper">
        <label for="todo-0" class="label__lg">
          What needs to be done?
        </label>
      </h2>
      <input type="text" id="todo-0" autocomplete="off"
        class="input input__lg"  bind:value={newTodo}/>
      <button type="submit" class="btn btn__primary btn__lg">
        Add
      </button>
    </form>
    {#each todoList as {task} }
      <div class="todo">
        <h3 class="task-text">{task}</h3>
        <button class="btn__danger">Remove Task</button>
      </div>
    {/each}
 </div>
  