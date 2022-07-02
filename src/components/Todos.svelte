<script>
    let todo = [];
    $:totalTodos = todo.length;
    let completedTodos;
    function addTodo(event){
        console.log(event.target)
    }
</script>

<div class="todo">
    <h2>What are we doing today?</h2>
    <h3>You have completed {completedTodos} out of {totalTodos}</h3>
    <form on:submit|preventDefault = {addTodo}>
        <input type="text" placeholder="What are we doing today?">
        <button type="submit">Add Todo</button>
    </form>
</div>