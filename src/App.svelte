<script>
  import Start from "./lib/Start.svelte";
  import Select from "./lib/Select.svelte";
  let start = true;

  function startDisappear() {
    start = !start;
  }
    
</script>

<style>
  :global(body) {
    margin: 0;
    font-family: 'Arial', sans-serif;
    background: linear-gradient(to right, #FB5E05, #7102FF);
    }
</style>

<main>
  {#if !start}
    <Select/>
  {:else}
    <Start on:click={startDisappear}/>
  {/if}
  
</main>
