<script>
  import { fly } from "svelte/transition"
  import MainFunnyPage from "./funnypages/main-funny-page.svelte"

	let pageCount = 0

	const handlePage = () => pageCount++

	let visible = true
</script>

<main class="page-wrapper" on:click={handlePage}>
	<MainFunnyPage {pageCount} {handlePage} />

	<h6 class="muted">Click dong layarnya</h6>
</main>


<style>

</style>