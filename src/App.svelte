<script>
  import Start from "./lib/Start.svelte";
  import Select from "./lib/Select.svelte";
  import { store } from "./script/stores";
  import Gpt from "./lib/gpt.svelte";
  import Generate from "./lib/Generate.svelte";
  import Load from "./lib/Load.svelte";
  
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
    background-size: cover;
    }
    

</style>

<main>
  
  {#if cm == 0}
    <Start on:click={startDisappear}/>
  {:else if cm == 1}
    <Select />
  {:else if cm == 2}
    <Gpt/>
  {:else if cm == 3}
    <Generate/>
  {:else if $store.val == 4}
      <Load />
  {:else}
    <p>Something went wrong</p>
  {/if}
  
</main>
