<script>
  import {blur, slide} from "svelte/transition";
  import { result, store } from "../script/stores";
  import OpenAI from "openai";
    const openai = new OpenAI({
      apiKey: '',
      dangerouslyAllowBrowser: true
    });
    
    let word;
    export const btnsend = async () => {  
      let mymessage = "Mi devi aiutare, quì sotto ti darò il programma scolastico che contiene le materie e ogni argomento svolto per ogni materia. Devo fare l'esame di maturità e devo riuscire a collegare la parola:"
      mymessage += word + ", con un solo argomento per ogni materia. Il tuo compito è quello di riuscire a fare i collegamenti e devi darmi in output un elenco con le materie, per ogni materia deve essere indicato l'argomento collegato e la spiegazione del collegamento. Se non riesci a collegare nessun argomento di una materia con la parola, puoi sempre collegarti ad un argomento trattato di un altra materia, per esempio partendo dalla parola Francesco Ferdinando puoi collegarti a storia con la prima guerra mondiale e successivamente collegarti a italiano con ungaretti. Se proprio non è possibile nessun collegamento oppure la parola è una parola senza significato scrivi che non sei riuscito a trovare i collegamenti. Concludi la conversazione augurando un in bocca al lupo per l'esame. Programma:"
      mymessage += $store.array[0] + ": " + $store.array[1];
      mymessage += $store.array[2] + ": " + $store.array[3];
      mymessage += $store.array[4] + ": " + $store.array[5];
      mymessage += $store.array[6] + ": " + $store.array[7];
      mymessage += $store.array[8] + ": " + $store.array[9];
      mymessage += $store.array[10] + ": " + $store.array[11];
      
      if (word !== undefined && word !== '') { 
      try {
        const userMessage = mymessage;
        if (userMessage !== '') {
          $store.val = 4;
          
          
          const response = await openai.chat.completions.create({
            messages: [{ role: 'system', content: userMessage }],
            model: 'gpt-3.5-turbo',
          });
  
          $store.val = 3;
          const chatbotMessage = response.choices[0].message.content;
          $result = chatbotMessage;
        }
      } catch (err) {
        console.error(err);
      }
    }
    else{
      //alert
      var alert = document.getElementById("alert");
            alert.style.display = "block";
            setTimeout(function() {
            alert.style.display = "none";
            }, 4000); // 3000 millisecondi = 3 secondi
                

    }
    };

    function goBack(){
      $store.val = 1;
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
    /* Your styles here */.hero {
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      color: #fff;
      }
  
      .hero-content {
      text-align: center;
      width:85%;
      max-width: 1000px;
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
      .input-text{
        padding: 2vh 4vw;
        font-size: 2.5rem;
        background-color: white;
        color: black;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        font-family: "Lilita One", sans-serif;
        transition: 0.4s;
        transition-delay: calc((var(--n) - 1) * 0.1s);
        margin-bottom: 10vh;
        width: 80%;
      }
      .back{
        position: absolute;

        top: 0;
        left: 0;
        margin: 2%;
        cursor: pointer;
        color: white;
      }
      @media screen and (max-width: 987px) {
        .hero-content {
        width: 100%;
        
      }
      .input-text{
        font-size: 1.7rem;
        width: 80%;
      }
      }
  
      
      @media screen and (max-width: 600px) {

      .toast {
        width: 200px;
          
      }
      .hero-title {
          font-size: 5em;
      }
      .hero-content {
        width: 100%;
        
      }
  
      .hero-subtitle {
          font-size: 1em;
      }
  
      .hero-button {
          font-size: 1.5em;
      }
      .input-text{
        font-size: 1rem;
        width: 80%;
      }
      .back{
        width: 40px;
        height: 40px;
      }
      }

      
  </style>
  <!--
  <div id="chatDiv">
    {#each allchat as res_msg}
      <div class="message {res_msg.type}">
        <span class="whosend">
          {res_msg.type === 'user' ? 'You' : 'chatBot'}
        </span>
        {res_msg.text}
      </div>
    {/each}
  </div>-->
  <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADIAAAAyCAYAAAAeP4ixAAAACXBIWXMAAAsTAAALEwEAmpwYAAADKElEQVR4nO3ZX+jfUxzH8YMZIsKPNcQuuOCG2Vy4wZJ/hcjfYtqS1UrUfhfaUnax5AJtabVEKXfKn9QQSpT/4kYSIuY/m9TYDHvo7Pv+tOPb7/f9fb+/72fb99T3eff7fc55n9frc97nnPf5fFMaM6YecEqqHVyCn1Ot4CDcg38g1QhOwEsKUm3gQnwX+n+ozohOKt2NXaH9dZxUlREcj82heTc24NB4VocRnIcvQ+8vuKLr+WgbsTeV/gqt72HBFO1G1wiOxlNdqTR3mrajaQTn4ovQ9zuun6H96BnBndjZK5Wm6NPwEz7Hu3gGD+MOLJpuNvd1KmUewWF99u2HP/BCvKh57TtIe4Scg8+KVLphiJcxgbNwMVZgPd4oZlmUNM/nNqlFE3nqd8QAH+GM1oL/f5zDo7jchF8LU2/nSmGYwEfhySLgo3mwVtX3NrWsyAKhZWLQQHnqP9nTne24dZ+p7q1jLibxW2jZgsXVGSn0TODZ0PMnbqkitXpUEffF4ZuZHMnFPoCe66K6zoaWH5Dtty2wNIz8jSv394GYB92Gr/Ep3sfTeAC344I8xgB6VkXcrTh5IDMtlCgzkc2+g/vjwJwzQ9xc5mRezmtoNmYWF/eP/Jav7tPIAizEElwbJ/tDeBFfFQu5IV+Xs6nTe3wX+DHarhjYSAQ5Fs9FkCzgweZGOJ2RPrfZm/F4nBkNuyMNz5yiz43R5nscOcyWuKq4o7851Ye4fo109TkYl4WBXUUN9hiO69KQUzyzZlZGimDn45viqnv5sEa6+p+KJ/BvhPq2LChjPYka7YhhzUxEGS4GXIdD2jDSgLOLt5/T7d7i2Yfx/9vSsMQ0r47dJ/Ma5rdlJJPXYWwAzexsjDRcGX+/lWr6QIebio8eG+Ocy3Vh5rQ2B5qHV8u9tLXgAS4tzrTJ4ly5K7VJXiNY26RBq8GDXAkX5UqemcwrqcafFXQOVUU6b5+pKhjJH3p0bpQfl2mcv36mGsFFXUZmV7KMAjrFY8OGVCu4pjCyOdUK5kT5kvkg1Yy9O9iWVDO4KozsSDWDE5uiMtWOzqXvmAOtY8yYMWn/8B/TbS1rji7GgQAAAABJRU5ErkJggg==" class="back" on:click={goBack}>
  
    <div class="hero">
      <div class="toast active" id="alert" style="display: none;">
  
    <div class="toast-content">
      <i class="fas fa-solid fa-check check"></i>
  
      <div class="message">
        <span class="text text-1">Errore!</span>
        <span class="text text-2">Inserisci una parola</span>
      </div>
    </div>
    <i class="fa-solid fa-xmark close"></i>
  
    <!-- Remove 'active' class, this is just to show in Codepen thumbnail -->
    <div class="progress active"></div>
  </div>
      <div class="hero-content">
        <h1 class="hero-title" in:blur={{delay:725, duration:350}} out:blur={{duration:350}}>BAPP</h1>
        <p class="hero-subtitle"in:blur={{delay:850, duration:350}} out:blur={{duration:350}}>Inserisci il materiale e genera i collegamenti</p>
        <input type="text" class="input-text"in:slide={{delay:1000, duration:350}} out:slide={{duration:350}} bind:value={word} placeholder="Inserisci lo stimolo"><br>
        <button in:blur={{delay:725, duration:350}} out:blur={{duration:350}} class="hero-button" on:click={btnsend}>Genera</button>
      </div>
    </div>
  
  
