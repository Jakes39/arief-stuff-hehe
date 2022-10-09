<script>
  import { fade, fly } from "svelte/transition"
  import Funky from "../components/funky.svelte"

  export let handlePage
  export let pageCount

  // $: {console.log(pageCount)}

  let choice = null

  const handleChoice = (c) => {
    choice = c
    handlePage()
  }

  const handleContinue = () => {
    handlePage()
  }

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
<div class="wrapper" in:fly={{ duration: 600, y: 30 }} on:click|stopPropagation>
  <h1>Kamu ulang tahun kan?</h1>
  <div class="option-wrap">
    <button on:click={() => handleChoice(1)}>Rill 100%</button>
    <button on:click={() => handleChoice(2)}>fek, 100% fek</button>
  </div>
</div>
{:else if pageCount == 4}
<div class="wrapper" in:fly={{ duration: 600, y: 30 }} on:click|stopPropagation={() => handleChoice(0)} >
  {#if choice == 1}
  <h1>Nahh, karena kamu ultah..</h1>
  {:else if choice == 2}
  <h1>Mana mungkin, itu fek</h1>
  {/if}
</div>
{:else if pageCount == 5}
<div class="wrapper" in:fly={{ duration: 600, y: 30 }} >
  <h1>Saya pingin mengucapkan...</h1>
</div>
{:else if pageCount == 6}
<div class="wrapper" in:fly={{ duration: 600, y: 30 }} on:click|stopPropagation >
  <h1>Selamat hari raya id-<h1>
  <Funky on:handleContinue={handleContinue} />
</div>
{:else if pageCount == 7}
<div class="wrapper" in:fly={{ duration: 600, y: 30 }} >
  <h1>Selamat ulang tahun Itaa :3</h1>
</div>
{:else}
<div class="wrapper" in:fly={{ duration: 600, y: 30 }} >
  <h1>Habis</h1>
</div>
{/if}
