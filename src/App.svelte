<script>
  import Start from "./lib/Start.svelte";
  import Select from "./lib/Select.svelte";
  import { store } from "./script/stores";
  import Gpt from "./lib/gpt.svelte";
  import Generate from "./lib/Generate.svelte";
  function startDisappear(){
    $store.val = 1;
  }
  $: cm = $store.val;
</script>

<style>
  :global(body) {
    margin: 0;
    font-family: 'Arial', sans-serif;
    background: linear-gradient(to right, #FB5E05, #7102FF);
    }
</style>

<main>
  {#if cm == 0}
    <Start on:click={startDisappear}/>
  {:else if cm == 1}
    <Select/>
  {:else if cm == 2}
    <Gpt/>
  {:else if cm == 3}
    <Generate/>
  {:else}
    <p>Something went wrong</p>
  {/if}
  
</main>
