<script lang="ts">
import TodoItem from './TodoItem.svelte';

let { todos, toggleTodo, deleteTodo } = $props();
</script>


<ul class="py-4">
    {#each todos as todo, i}
      <TodoItem todo={todo} toggleTodo={toggleTodo} deleteTodo={deleteTodo} i={i} />
    {/each}
</ul>