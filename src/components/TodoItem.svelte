<script lang="ts">
let { todo, toggleTodo, deleteTodo, i  } = $props();
</script>

<li class="flex items-center justify-between px-1 py-1.5 border-b border-gray-200">
    <div class="flex items-center gap-2 w-full">
        <input type="checkbox" checked={todo.done} onchange={() => toggleTodo(i)} />
        <span style="text-decoration: {todo.done ? 'line-through' : 'none'}">
          {todo.text}
        </span>
    </div>
    <button class="w-[50px] text-red-500 text-sm border rounded" onclick={() => deleteTodo(i)}>삭제</button>
</li>
