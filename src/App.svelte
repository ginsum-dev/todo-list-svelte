<script lang="ts">
  import TodoInput from './components/TodoInput.svelte';
  import TodoList from './components/TodoList.svelte';

  let todos = $state([]); 

  function addTodo(value: string) {
    todos = [...todos, { text: value, done: false, createdAt: new Date().toISOString() }];
  }

  function toggleTodo(index) {
    todos = todos.map((todo, i) =>
      i === index ? { ...todo, done: !todo.done } : todo
    );
  }

  function deleteTodo(index) {
    todos = todos.filter((_, i) => i !== index);
  }
</script>

<main>
  <h1>📝 Todo List</h1>
  <TodoInput onAdd={addTodo} />
  <TodoList todos={todos} toggleTodo={toggleTodo} deleteTodo={deleteTodo} />
</main>
