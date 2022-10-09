<script>
  import P1 from "./P1.svelte"
  import P2 from "./P2.svelte"
  import P3 from "./p3.svelte"

  export let pageCount = 0
</script>

<page>
  {#if pageCount == 0}
  <P1 />
  {:else if pageCount == 1}
  <P2 />
  {:else if pageCount == 2}
  <P3 /> 
  {:else}
  <h1>habis :(</h1>
  {/if}
</page>