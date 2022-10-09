<script>
  import MainFunnyPage from "./funnypages/main-funny-page.svelte"

	let pageCount = 0

	const handlePage = () => pageCount++

</script>

<main>
	<h2>Why no work</h2>
	<div class="page-wrapper" on:click={handlePage} >
		<MainFunnyPage {pageCount} />
	</div>
</main>

<style>

</style>