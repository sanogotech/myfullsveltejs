<script>
  import Sidebar from './Sidebar.svelte';
  import TodoView from './TodoView.svelte';

  var currentTodo = '';

  function viewTodo(todo) {
    currentTodo = todo;
  }

  function removeTodo() {
    currentTodo = ''
  }
</script>


<TodoView currentTodo={currentTodo}/>
<Sidebar viewTodo={viewTodo} removeTodo={removeTodo}/>