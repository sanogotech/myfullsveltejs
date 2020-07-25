<script>
  import Todo from './Todo.svelte';

  export let viewTodo;
  export let removeTodo;

  let todo = '';
  let todoList = [];
  function addTodo(e) {
    if (e.keyCode === 13) {
      todoList = todoList.concat(todo);
      todo = '';
    }
  }

  function todoDone(key) {
    var temp = todoList;
    temp.splice(key, 1);
    todoList = temp;
    removeTodo();
  }
</script>

<style>
  .sidebar-container {
    position: fixed;
    right: 0;
    width: 400px;
    height: 100vh;
    background-color: #fff;
    top: 0;
    z-index: 999;
    box-shadow: 1px 1px 20px #000;
  }
  .todo-input {
    width: 100%;
    height: 5%;
  }
  input {
    color: rgb(56, 56, 56);
    font-weight: 70;
    font-size: 15px;
  }
  input::placeholder {
    color: rgb(165, 165, 165);
    font-weight: 70;
    font-size: 15px;
  }
  .empty-todo {
    padding: 10px;
    height: 100%;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    color: rgb(133, 133, 133);
    font-weight: 70;
    font-size: 15px;
  }
  .todo-list-container {
    overflow-y: scroll;
    height: 95%;
  }
</style>

<div class="sidebar-container">
  <input 
    placeholder="Enter todo list" 
    type="text" 
    class="todo-input" 
    bind:value={todo} 
    on:keydown={addTodo}
  >
  <div class="todo-list-container">
    {#if !todoList.length}
      <div class="empty-todo">No Todos yet!</div>
      {:else}
      {#each todoList as todo,i }
        <Todo 
          todo={todo} 
          key={i} 
          viewTodo={viewTodo} 
          todoDone={todoDone}
        /> 
      {/each}
    {/if}
  </div>
</div>