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
  <input
  placeholder="할 일을 입력하세요"
  bind:value={newTodo}
  on:keydown={(e) => e.key === 'Enter' && addTodo()}
/>
<button on:click={addTodo}>추가</button>

<ul>
  {#each todos as todo, i}
    <li>
      <input type="checkbox" bind:checked={todo.done} on:change={() => toggleTodo(i)} />
      <span style="text-decoration: {todo.done ? 'line-through' : 'none'}">
        {todo.text}
      </span>
      <button on:click={() => deleteTodo(i)}>삭제</button>
    </li>
  {/each}
</ul>
</main>

<style>

</style>
