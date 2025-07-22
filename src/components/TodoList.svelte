<script lang="ts">
import TodoItem from './TodoItem.svelte';

let { todos, toggleTodo, deleteTodo } = $props();
</script>


<ul>
    {#each todos as todo, i}
      <TodoItem todo={todo} toggleTodo={toggleTodo} deleteTodo={deleteTodo} i={i} />
    {/each}
</ul>