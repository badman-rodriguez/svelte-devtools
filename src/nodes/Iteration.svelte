<script>
  export let style
  export let hover
  export let selected
  export let source
</script>

<style>
  div {
    height: 16px;
    line-height: 16px;
  }

  div {
    color: rgb(151, 164, 179);
  }

  :global(.dark) div {
    color: rgb(175, 181, 191);
  }
</style>

<div class:hover class:selected {style}>&#8618;</div>
<slot />
