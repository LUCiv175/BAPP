<script>

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
  <div class="hero">
    <div class="hero-content">
      <h1 class="hero-title">BAPP</h1>
      <p class="hero-subtitle">Il migliore amico della tua maturita!</p>
      <button class="hero-button" on:click>Iniziamo</button>
    </div>
  </div>

