<script lang="ts">
let { todo, toggleTodo, deleteTodo, i  } = $props();
</script>

<li>
    <input type="checkbox" checked={todo.done} onchange={() => toggleTodo(i)} />
    <span style="text-decoration: {todo.done ? 'line-through' : 'none'}">
      {todo.text}
    </span>
    <button onclick={() => deleteTodo(i)}>삭제</button>
</li>
