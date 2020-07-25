<script>
  let width = document.body.clientWidth;
  width = width - 400;
  
  export let currentTodo;

  var extras = [];

  var currentTodoExtra = extras[currentTodo] ? extras[currentTodo] : 'Sample';
</script>

<style>
  .view-todo-container {
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .current-todo-wrapper {
    background-color: #fff;
    height: 95%;
    width: 95%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    box-shadow: 0px 0px 20px #000;
    border-top-right-radius: 40px;
  }
  .current-todo-item {
    color: rgb(56, 56, 56);
    font-size: 40px;
    font-weight: 100;
  }
</style>

<div class="view-todo-container" style={`width:${width}px`}>
  {#if currentTodo.length}
    <div class="current-todo-wrapper">
      <div class="current-todo-item">{currentTodo}</div>
    </div>
  {/if}
</div>