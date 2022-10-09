<script>
  import { createEventDispatcher } from "svelte"

  let dispatch = createEventDispatcher()

  export let delay = 1000

  setTimeout(() => {
    dispatch('handleContinue')
  }, delay)
</script>