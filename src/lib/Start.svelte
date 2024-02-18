<script>
import {blur} from "svelte/transition";
</script>

<style>
    .hero {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    color: #fff;
    }

    .hero-content {
    text-align: center;
    }

    .hero-title {
    font-size: 7em;
    margin-bottom: 3vh;
    font-family: "Lilita One", sans-serif;
    }

    .hero-subtitle {
    font-size: 1.5em;
    margin-bottom: 10vh;
    font-family: "Lilita One", sans-serif;
    }

    .hero-button {
    padding: 2vh 4vw;
    font-size: 2.5em;
    background-color: white;
    color: black;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    font-family: "Lilita One", sans-serif;
    transition: 0.4s;
    transition-delay: calc((var(--n) - 1) * 0.1s);
    }
    .hero-button:hover{
      background-color: rgba(128, 128, 128, 0.479);
      color: #fff;
      transform: scale(1.1);
    }

    
    @media screen and (max-width: 600px) {
    .hero-title {
        font-size: 5em;
    }

    .hero-subtitle {
        font-size: 1em;
    }

    .hero-button {
        font-size: 1.5em;
    }
    }


  
</style>
  <div class="hero" in:blur={{delay:400, duration:350}} out:blur={{duration:500}}>
    <div class="hero-content">
      <h1 class="hero-title">BAPP</h1>
      <p class="hero-subtitle">Il migliore amico della tua maturita!</p>
      <button class="hero-button" on:click>Iniziamo</button>
    </div>
  </div>

