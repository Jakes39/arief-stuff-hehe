<script>
  import { fade, fly } from "svelte/transition"

  export let pageCount = 0
</script>

{#if pageCount == 0}
<div class="wrapper" in:fade={{duration: 600}} >
  <h1>Umm</h1>
</div>
{:else if pageCount == 1}
<div class="wrapper" in:fly={{ duration: 600, y: 30 }} >
  <h1>Hello Itaaa</h1>
</div>
{:else if pageCount == 2}
<div class="wrapper" in:fly={{ duration: 600, y: 30 }} >
  <h1>Jadi gini...</h1>
</div>
{:else if pageCount == 3}
<div class="wrapper" in:fly={{ duration: 600, y: 30 }} >
  <h1>Kamu ulang tahun kan?</h1>
  <h3 class="down50 muted">No fek fek?</h3>
</div>
{:else}
<div class="wrapper" in:fly={{ duration: 600, y: 30 }} >
  <h1>Habis</h1>
</div>
{/if}
