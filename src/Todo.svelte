<script>
  export let todo;
  export let key;
  export let todoDone;
  export let viewTodo;

  const completedMessage = [
    "I'm Done!",
    "Accomplished!",
    "Finished!",
    "Done and dusted!",
    "Done for the day!",
    "Peace out!",
    "Cash me outside!"
  ]

  function setRandomCompletedMessage() {
    var index = Math.floor(Math.random() * 7);
    return completedMessage[index]
  }
</script>

<style>
  .todo-item-wrapper {
    padding: 10px;
    color: rgb(65, 65, 65);
    font-weight: 70;
    font-size: 15px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .todo-item {
    cursor: pointer;
  }
  .done-btn {
    background-color: #fff;
    border-radius: 15px;
    color: rgb(65, 65, 65);
    cursor: pointer;
  }
</style>

<div class="todo-item-wrapper">
  <div 
    class="todo-item" 
    on:click={viewTodo.bind(this, todo)}
  >
    {todo}
  </div>
  <button 
    class="done-btn" 
    on:click={todoDone.bind(this, key)}
  >
    {setRandomCompletedMessage()}
  </button>
</div>