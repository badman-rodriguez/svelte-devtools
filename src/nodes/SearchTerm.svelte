<script>
  import { searchValue } from '../store.js'

  export let text

  $: i = text.indexOf($searchValue)
  $: pre = text.substring(0, i)
  $: highlight = text.substring(i, i + $searchValue.length)
  $: post = text.substring(i + $searchValue.length)
</script>

<style>
  span {
    background-color: yellow !important;
    color: black !important;
  }
</style>

{#if i == -1 || $searchValue.length < 2}
  {text}
{:else}
  {pre}
  <span>{highlight}</span>
  {post}
{/if}
