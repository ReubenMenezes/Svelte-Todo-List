<script>
    let todoList = []
    let newTodo = " ";
    function addTodoItem(){
      if(newTodo.trim().length === 0){
        return
      }
        todoList = [...todoList,{task:newTodo}]
        newTodo = ""
    }
    function removeTodoItem(index){
      todoList.splice(index, 1)
      todoList = [...todoList]
    }
</script>

<style>
    @import "../global.css";
</style>

<div class="todoapp stack-large">
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
    {#each todoList as {task}, i }
      <div class="todo">
        <h3 class="task-text">{task}</h3>
        <button class="btn__danger" on:click={() => removeTodoItem(i)}>Remove Task</button>
      </div>
    {/each}
 </div>
  