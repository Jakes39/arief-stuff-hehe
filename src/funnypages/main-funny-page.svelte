<script>
  import { fade, fly } from "svelte/transition"
  import Funky from "../components/funky.svelte"

  export let handlePage
  export let pageCount


  const defaultFly = { duration: 600, y: 30 }

  // $: {console.log("Page: " + pageCount)}

  let choice = null

  export let alternative = 0

  // $: {console.log("Alternate: " + alternative)}

  const handleChoice = (c) => {
    choice = c
    handlePage()
  }

  const handleAlternate = (c) => {
    if (c > 0) { alternative = c }
    else { alternative = 0; handlePage()}
  }

</script>

{#if pageCount == 0}
<div class="wrapper" in:fade={{duration: 600}}>
  <h1>Umm</h1>
</div>

{:else if pageCount == 1}
<div class="wrapper" in:fly={defaultFly} >
  <h1>Hello Itaaa</h1>
</div>

{:else if pageCount == 2}
<div class="wrapper" in:fly={defaultFly} >
  <h1>Jadi gini...</h1>
</div>

{:else if pageCount == 3}
<div class="wrapper" in:fly={defaultFly} on:click|stopPropagation>
  <h1>Kamu ulang tahun kan?</h1>
  <div class="option-wrap">
    <button on:click|stopPropagation={() => handleChoice(1)}>Rill 100%</button>
    <button on:click|stopPropagation={() => handleChoice(2)}>fek, 100% fek</button>
  </div>
</div>

{:else if pageCount == 4 && alternative == 0}
  {#if choice == 1}
    <div class="wrapper" in:fly={defaultFly}>
      <h1>Nahh, karena kamu ulang tahun..</h1>
    </div>
  {:else}
    <div class="wrapper" in:fly={defaultFly} on:click|stopPropagation={() => handleAlternate(1)}>
      <h1>Fek, tidak mungkin tu</h1>
    </div>
  {/if}

{:else if pageCount == 4 && alternative == 1}
  <div class="wrapper" in:fly={defaultFly} on:click|stopPropagation={() => handleAlternate(0)}>
    <h1>Ehem, jadi gini...</h1>
  </div>

{:else if pageCount == 5}
<div class="wrapper" in:fly={defaultFly} >
  <h1>Saya pingin mengucapkan...</h1>
</div>

{:else if pageCount == 6}
<div class="wrapper" in:fly={defaultFly} on:click|stopPropagation >
  <h1>Selamat hari raya id-<h1>
  <Funky on:handleContinue={handlePage} />
</div>

{:else if pageCount == 7}
<div class="wrapper" in:fly={defaultFly} on:click|stopPropagation >
  <h1>Eh<h1>
  <Funky on:handleContinue={handlePage} delay=1500 />
</div>

{:else if pageCount == 8}
<div class="wrapper" in:fly={defaultFly} >
  <h1>Selamat ulang tahun Itaa :3</h1>
</div>

{:else}
<div class="wrapper" in:fly={defaultFly} >
  <h1>Habis</h1>
</div>
{/if}
