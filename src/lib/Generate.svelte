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
    margin-bottom: 5vh;
    font-family: "Lilita One", sans-serif;
    }

    
    .hero-subtitle {
    font-size: 1.5em;
    margin-bottom: 3vh;
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

    .outputChat{
      width: 50vw;
      height: 40vh;
      display: flex;
      justify-content: center;
      align-items: center;
      margin-bottom: 10vh;
      border-radius: 10px;
      resize: none;
    }

    
    @media screen and (max-width: 600px) {
        .hero-title {
            font-size: 5em;
        }
        .outputChat{
          width: 90vw;

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
      <p class="hero-subtitle">I tuoi collegamenti</p>
      <textarea class="outputChat" id="outputChat" cols="30" rows="10" disabled
      ></textarea>
      <button class="hero-button" on:click>Torna alla home</button>
      
    </div>
  </div>

