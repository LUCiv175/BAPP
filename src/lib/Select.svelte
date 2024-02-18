<script>
    import { store } from "../script/stores";
    import {scale, blur, slide} from "svelte/transition";
    $:pippo = 0;
    

    function returnBack(){
        $store.val = 0;
    }

    function save(){
        if(prompt.length < 12){
            pippo=1;
            setTimeout(function() {
            pippo=0;
            }, 4000); // 3000 millisecondi = 3 secondi
                }
        else{
            $store.val = 2;
            $store.array = prompt;
        }
    }
    let prompt = [];
    if($store.array.length > 0){
        prompt = $store.array;
    }
    function hideAlert() {
    document.getElementById("alert").style.display = "none";
  }

  
</script>

<style>
  .toast {
  position: fixed;
  top: 10px;
  width: 300px;
  border-radius: 12px;
  background: rgba(0, 0, 0, 0.893);
  padding: 20px 35px 20px 25px;
  box-shadow: 0 6px 20px -5px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transform: translateX(calc(100% + 30px));
  transition: all 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.35);
}

.toast.active {
  transform: translateX(0%);
}

.toast .toast-content {
  display: flex;
  align-items: center;
}

.toast-content .check {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 35px;
  min-width: 35px;
  background-color: rgb(216, 3, 3);
  color: white;
  font-size: 20px;
  border-radius: 50%;
}

.toast-content .message {
  display: flex;
  flex-direction: column;
  margin: 0 20px;
}

.message .text {
  font-size: 16px;
  font-weight: 400;
  color: rgb(253, 243, 243);
}

.message .text.text-1 {
  font-weight: 600;
  color: rgb(253, 243, 243);
}

.toast .close {
  position: absolute;
  top: 10px;
  right: 15px;
  padding: 5px;
  cursor: pointer;
  opacity: 0.7;
}

.toast .close:hover {
  opacity: 1;
}

.toast .progress {
  position: absolute;
  bottom: 0;
  left: 0;
  height: 3px;
  width: 100%;

}

.toast .progress:before {
  content: "";
  position: absolute;
  bottom: 0;
  right: 0;
  height: 100%;
  width: 100%;
  background-color: rgb(216, 3, 3);
}

.progress.active:before {
  animation: progress 4s linear forwards;
}

@keyframes progress {
  100% {
    right: 100%;
  }
}


.toast.active ~ button {
  pointer-events: none;
}
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

    .toast {
        width: 200px;
    }
  
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
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADIAAAAyCAYAAAAeP4ixAAAACXBIWXMAAAsTAAALEwEAmpwYAAADKElEQVR4nO3ZX+jfUxzH8YMZIsKPNcQuuOCG2Vy4wZJ/hcjfYtqS1UrUfhfaUnax5AJtabVEKXfKn9QQSpT/4kYSIuY/m9TYDHvo7Pv+tOPb7/f9fb+/72fb99T3eff7fc55n9frc97nnPf5fFMaM6YecEqqHVyCn1Ot4CDcg38g1QhOwEsKUm3gQnwX+n+ozohOKt2NXaH9dZxUlREcj82heTc24NB4VocRnIcvQ+8vuKLr+WgbsTeV/gqt72HBFO1G1wiOxlNdqTR3mrajaQTn4ovQ9zuun6H96BnBndjZK5Wm6NPwEz7Hu3gGD+MOLJpuNvd1KmUewWF99u2HP/BCvKh57TtIe4Scg8+KVLphiJcxgbNwMVZgPd4oZlmUNM/nNqlFE3nqd8QAH+GM1oL/f5zDo7jchF8LU2/nSmGYwEfhySLgo3mwVtX3NrWsyAKhZWLQQHnqP9nTne24dZ+p7q1jLibxW2jZgsXVGSn0TODZ0PMnbqkitXpUEffF4ZuZHMnFPoCe66K6zoaWH5Dtty2wNIz8jSv394GYB92Gr/Ep3sfTeAC344I8xgB6VkXcrTh5IDMtlCgzkc2+g/vjwJwzQ9xc5mRezmtoNmYWF/eP/Jav7tPIAizEElwbJ/tDeBFfFQu5IV+Xs6nTe3wX+DHarhjYSAQ5Fs9FkCzgweZGOJ2RPrfZm/F4nBkNuyMNz5yiz43R5nscOcyWuKq4o7851Ye4fo109TkYl4WBXUUN9hiO69KQUzyzZlZGimDn45viqnv5sEa6+p+KJ/BvhPq2LChjPYka7YhhzUxEGS4GXIdD2jDSgLOLt5/T7d7i2Yfx/9vSsMQ0r47dJ/Ma5rdlJJPXYWwAzexsjDRcGX+/lWr6QIebio8eG+Ocy3Vh5rQ2B5qHV8u9tLXgAS4tzrTJ4ly5K7VJXiNY26RBq8GDXAkX5UqemcwrqcafFXQOVUU6b5+pKhjJH3p0bpQfl2mcv36mGsFFXUZmV7KMAjrFY8OGVCu4pjCyOdUK5kT5kvkg1Yy9O9iWVDO4KozsSDWDE5uiMtWOzqXvmAOtY8yYMWn/8B/TbS1rji7GgQAAAABJRU5ErkJggg==" class="back" on:click={returnBack}>

<div class="hero">
    {#if pippo==1}
    <div class="toast active" id="alert"  in:slide={{delay:100, duration:350}} out:slide={{duration:350}}>
  
    <div class="toast-content" >
      <i class="fas fa-solid fa-check check"></i>
  
      <div class="message" >
        <span class="text text-1">Errore!</span>
        <span class="text text-2">Inserisci tutte le materie e i relativi programmi</span>
      </div>
    </div>
    <i class="fa-solid fa-xmark close"></i>
  
    <!-- Remove 'active' class, this is just to show in Codepen thumbnail -->
    <div class="progress active"></div>
  </div>
    {/if}
    <div class="hero-content">  
        <h1 class="hero-title" in:blur={{delay:550, duration:350}} out:blur={{duration:350}}>BAPP</h1>
        <p class="hero-subtitle" in:blur={{delay:675, duration:350}} out:blur={{duration:350}}>Inserisci le materie e i programmi</p>
        <div class="grid-container" in:scale={{delay:800, duration:400}} out:scale={{duration:400}}>
          <div class="grid-item"><input class="hero-input" type="text" bind:value={prompt[0]}  placeholder="Inserisci Materia" /><br><textarea  class="hero-input-text"  bind:value={prompt[1]} placeholder="Inserisci programma" rows="4" cols="50"/></div>
          <div class="grid-item"><input class="hero-input" type="text" bind:value={prompt[2]}  placeholder="Inserisci Materia" /><br><textarea  class="hero-input-text"  bind:value={prompt[3]} placeholder="Inserisci programma" rows="4" cols="50"/></div>
          <div class="grid-item"><input class="hero-input" type="text" bind:value={prompt[4]}  placeholder="Inserisci Materia" /><br><textarea  class="hero-input-text"  bind:value={prompt[5]} placeholder="Inserisci programma" rows="4" cols="50"/></div>
          <div class="grid-item"><input class="hero-input" type="text" bind:value={prompt[6]}  placeholder="Inserisci Materia" /><br><textarea  class="hero-input-text"  bind:value={prompt[7]} placeholder="Inserisci programma" rows="4" cols="50"/></div>
          <div class="grid-item"><input class="hero-input" type="text" bind:value={prompt[8]}  placeholder="Inserisci Materia" /><br><textarea  class="hero-input-text"  bind:value={prompt[9]} placeholder="Inserisci programma" rows="4" cols="50"/></div>
          <div class="grid-item"><input class="hero-input" type="text" bind:value={prompt[10]}  placeholder="Inserisci Materia" /><br><textarea  class="hero-input-text"  bind:value={prompt[11]} placeholder="Inserisci programma" rows="4" cols="50"/></div>
        </div>
        <button class="hero-button" in:blur={{delay:675, duration:350}} out:blur={{duration:350}} on:click={save}>Salva</button>
    </div>
</div>

