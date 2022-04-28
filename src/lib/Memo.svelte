<script lang="ts">
  let memoList:string[] = []
  $: count = memoList.length
  let value: string = ''
  $: disabled = value.length === 0

  const increment = () => {
    memoList = [...memoList, value]
    value = ''
  }
</script>

<input type='text' bind:value />
<button on:click={increment} disabled={disabled}>
  메모추가: {count}
</button>
{#each memoList as memo}
<p>{memo}</p>
{/each}