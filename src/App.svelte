<script lang="ts">
  import TodoInput from './components/TodoInput.svelte';
 
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

<ul>
  {#each todos as todo, i}
    <li>
      <input type="checkbox" bind:checked={todo.done} onchange={() => toggleTodo(i)} />
      <span style="text-decoration: {todo.done ? 'line-through' : 'none'}">
        {todo.text}
      </span>
      <button onclick={() => deleteTodo(i)}>삭제</button>
    </li>
  {/each}
</ul>
</main>

<style>
input {
    margin-right: 10px;
  }
  li {
    margin-top: 10px;
  }
  button {
    margin-left: 10px;
  }
</style>
