<script>
  import MainFunnyPage from "./funnypages/main-funny-page.svelte"

	let pageCount = 0

	const handlePage = () => pageCount++

</script>

<main>
	<div class="page-wrapper" on:click={handlePage} >
		<MainFunnyPage {pageCount} />
	</div>
</main>

<style>

</style>