<script>
  // import svelteLogo from './assets/svelte.svg'
  // import viteLogo from '/vite.svg'
  // import Counter from './lib/Counter.svelte'
  let newTodo = '';
  let todos = [];
  function addTodo() {
    if (newTodo.trim() === '') return;
    todos = [...todos, { text: newTodo, done: false }];
    newTodo = '';
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
</main>

<style>

</style>
