<script lang="ts">
let { onAdd } = $props();
let input = $state('');

function handleAdd() {
  if (!input.trim()) return;
  onAdd(input);
  input = '';
}
</script>

<div class="flex gap-2">
  <input
    class="border border-gray-300 px-2 py-1 rounded w-full"
    bind:value={input}
    onkeydown={(e) => e.key === 'Enter' && handleAdd()}
    placeholder="할 일을 입력하세요"
  />
  <button class="w-[80px] bg-blue-600 text-white px-3 py-1 rounded" onclick={handleAdd}>추가</button>
</div>
