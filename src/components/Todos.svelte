<script>
    let task;
    let todo = [];
    let totalTodos = todo.length;
    let completedTodos = 0;
    function addTodo(){
        todo = [...todo,{task,completed:false}]
        console.log(todo[0])
    }
</script>

<div class="todo">
    <h2>What are we doing today?</h2>
    <h3>You have completed {completedTodos} out of {totalTodos}</h3>
    <form on:submit={addTodo}>
        <input type="text" placeholder="What are we doing today?"  bind:value = {task}>
        <button type="submit">Add Todo</button>
    </form>    
    <h2>{todo[0]}</h2>
</div>