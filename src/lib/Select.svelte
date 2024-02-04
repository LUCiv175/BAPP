<script>
    export let val = 0;

    let inputValue = '';

    function handleInput(event) {
        inputValue = event.target.value;
    }
</script>

<style>
    .hero {
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
        margin-bottom: 5vh;
        font-family: "Lilita One", sans-serif;
    }

    .hero-button {
        padding: 2vh 4vw;
        margin-top: 3vh;
        margin-bottom: 3vh;
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

  

    .hero-input {
        margin: 10px;
        margin-bottom: 5px;
        padding: 2vh 4vw;
        font-size: 2em;
        background-color: white;
        color: black;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        font-family: "Lilita One", sans-serif;
        width: 21vw;
        transition: 0.4s;
        transition-delay: calc((var(--n) - 1) * 0.1s);
    }

    .hero-content{
        width: 100%;
    }

    

    .hero-input-text {
        margin: 10px;
        margin-top:5px ;
        margin-bottom: 15px;
        padding: 2vh 4vw;
        font-size: 2em;
        background-color: white;
        color: black;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        font-family: "Lilita One", sans-serif;
        width: 21vw;
        height: 30vh;
        resize: none;
        transition: 0.4s;
        transition-delay: calc((var(--n) - 1) * 0.1s);
    }

    .grid-container {
        width: 100%;
        display: grid;
        grid-template-columns: repeat(3, 1fr); 
        gap: 10px;
        
}

  .grid-item {
    justify-content: center;
    width: 100%;
    color: white;
    }
    .back{
        position: absolute;

        top: 0;
        left: 0;
        margin: 2%;
        cursor: pointer;
        color: white;
      }
      .hero-button:hover{
        background-color: rgba(128, 128, 128, 0.479);
        color: #fff;
        transform: scale(1.1);
      }
      @media screen and (max-width: 1160px) {
        .grid-container {
        grid-template-columns: repeat(2, 1fr); 
        gap: 20px;
        justify-items: center;
        }
        .hero-input, .hero-input-text{
            width: 100%;
            font-size: 1.2em;
            
        }
        .grid-item {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            width: 100%;
            color: white;
            }

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

    .grid-container {
        grid-template-columns: repeat(1, 1fr); 
        gap: 20px;
        justify-items: center;


  }
  .hero-input, .hero-input-text{
    width: 100%;
    font-size: 1.2em;
    
  }
  .grid-item {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    width: 100%;
    color: white;
    }
    .back{
        width: 40px;
        height: 40px;
      }
}
  
</style>
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADIAAAAyCAYAAAAeP4ixAAAACXBIWXMAAAsTAAALEwEAmpwYAAADKElEQVR4nO3ZX+jfUxzH8YMZIsKPNcQuuOCG2Vy4wZJ/hcjfYtqS1UrUfhfaUnax5AJtabVEKXfKn9QQSpT/4kYSIuY/m9TYDHvo7Pv+tOPb7/f9fb+/72fb99T3eff7fc55n9frc97nnPf5fFMaM6YecEqqHVyCn1Ot4CDcg38g1QhOwEsKUm3gQnwX+n+ozohOKt2NXaH9dZxUlREcj82heTc24NB4VocRnIcvQ+8vuKLr+WgbsTeV/gqt72HBFO1G1wiOxlNdqTR3mrajaQTn4ovQ9zuun6H96BnBndjZK5Wm6NPwEz7Hu3gGD+MOLJpuNvd1KmUewWF99u2HP/BCvKh57TtIe4Scg8+KVLphiJcxgbNwMVZgPd4oZlmUNM/nNqlFE3nqd8QAH+GM1oL/f5zDo7jchF8LU2/nSmGYwEfhySLgo3mwVtX3NrWsyAKhZWLQQHnqP9nTne24dZ+p7q1jLibxW2jZgsXVGSn0TODZ0PMnbqkitXpUEffF4ZuZHMnFPoCe66K6zoaWH5Dtty2wNIz8jSv394GYB92Gr/Ep3sfTeAC344I8xgB6VkXcrTh5IDMtlCgzkc2+g/vjwJwzQ9xc5mRezmtoNmYWF/eP/Jav7tPIAizEElwbJ/tDeBFfFQu5IV+Xs6nTe3wX+DHarhjYSAQ5Fs9FkCzgweZGOJ2RPrfZm/F4nBkNuyMNz5yiz43R5nscOcyWuKq4o7851Ye4fo109TkYl4WBXUUN9hiO69KQUzyzZlZGimDn45viqnv5sEa6+p+KJ/BvhPq2LChjPYka7YhhzUxEGS4GXIdD2jDSgLOLt5/T7d7i2Yfx/9vSsMQ0r47dJ/Ma5rdlJJPXYWwAzexsjDRcGX+/lWr6QIebio8eG+Ocy3Vh5rQ2B5qHV8u9tLXgAS4tzrTJ4ly5K7VJXiNY26RBq8GDXAkX5UqemcwrqcafFXQOVUU6b5+pKhjJH3p0bpQfl2mcv36mGsFFXUZmV7KMAjrFY8OGVCu4pjCyOdUK5kT5kvkg1Yy9O9iWVDO4KozsSDWDE5uiMtWOzqXvmAOtY8yYMWn/8B/TbS1rji7GgQAAAABJRU5ErkJggg==" class="back">

<div class="hero">
    <div class="hero-content">
        <h1 class="hero-title">BAPP</h1>
        <p class="hero-subtitle">Inserisci le materie e i programmi</p>
        <div class="grid-container">
          <div class="grid-item"><input class="hero-input" type="text" bind:value={inputValue} on:input={handleInput} placeholder="Inserisci Materia" /><br><textarea  class="hero-input-text"  bind:value={inputValue} on:input={handleInput} placeholder="Inserisci programma" rows="4" cols="50"/></div>
          <div class="grid-item"><input class="hero-input" type="text" bind:value={inputValue} on:input={handleInput} placeholder="Inserisci Materia" /><br><textarea  class="hero-input-text"  bind:value={inputValue} on:input={handleInput} placeholder="Inserisci programma" rows="4" cols="50"/></div>
          <div class="grid-item"><input class="hero-input" type="text" bind:value={inputValue} on:input={handleInput} placeholder="Inserisci Materia" /><br><textarea  class="hero-input-text"  bind:value={inputValue} on:input={handleInput} placeholder="Inserisci programma" rows="4" cols="50"/></div>
          <div class="grid-item"><input class="hero-input" type="text" bind:value={inputValue} on:input={handleInput} placeholder="Inserisci Materia" /><br><textarea  class="hero-input-text"  bind:value={inputValue} on:input={handleInput} placeholder="Inserisci programma" rows="4" cols="50"/></div>
          <div class="grid-item"><input class="hero-input" type="text" bind:value={inputValue} on:input={handleInput} placeholder="Inserisci Materia" /><br><textarea  class="hero-input-text"  bind:value={inputValue} on:input={handleInput} placeholder="Inserisci programma" rows="4" cols="50"/></div>
          <div class="grid-item"><input class="hero-input" type="text" bind:value={inputValue} on:input={handleInput} placeholder="Inserisci Materia" /><br><textarea  class="hero-input-text"  bind:value={inputValue} on:input={handleInput} placeholder="Inserisci programma" rows="4" cols="50"/></div>
        </div>
        <button class="hero-button" on:click>Salva</button>
    </div>
</div>

