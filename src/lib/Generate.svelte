<script>
    import { store, result } from "../script/stores";
    function backToHome(){
        $store.val = 0;
        $store.array = [];
    }
    function goBack(){
        $store.val = 2;
    }

    let res = $result;
</script>

<style>
    .hero {
    display: flex;
    justify-content: center;
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
      transition: 0.4s;
      transition-delay: calc((var(--n) - 1) * 0.1s);
      }
      .hero-button:hover{
        background-color: rgba(128, 128, 128, 0.479);
        color: #fff;
        transform: scale(1.1);
      }
    .back{
        position: absolute;

        top: 0;
        left: 0;
        margin: 2%;
        cursor: pointer;
        color: white;
      }

    .outputChat{
      width: 50vw;
      height: 40vh;
      display: flex;
      padding: 10px;
      justify-content: center;
      align-items: center;
      margin-bottom: 10vh;
      border-radius: 10px;
      resize: none;
      color: white;
      font-family: 'Times New Roman', Times, serif;
      font-size: 1em;
      overflow-x: hidden;
    }
    .outputChat::-webkit-scrollbar {
      display: none;
    }
    
    @media screen and (max-width: 600px) {
        .hero-title {
            font-size: 5em;
        }
        
        .outputChat{
          font-size: 0.8em;
          width: 80vw;
        }

        .hero-subtitle {
            font-size: 1em;
        }

        .hero-button {
            font-size: 1.5em;
        }
        .back{
        width: 40px;
        height: 40px;
      }
    }
    @media screen and (max-width: 350px) {
        .outputChat{
          padding: 0px;
        }
        .outputChat{
          width: 100%;
          font-size: 0.65em;

        }
        .hero-content {
        width: 90%;
        }
    }


  
</style>
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADIAAAAyCAYAAAAeP4ixAAAACXBIWXMAAAsTAAALEwEAmpwYAAADKElEQVR4nO3ZX+jfUxzH8YMZIsKPNcQuuOCG2Vy4wZJ/hcjfYtqS1UrUfhfaUnax5AJtabVEKXfKn9QQSpT/4kYSIuY/m9TYDHvo7Pv+tOPb7/f9fb+/72fb99T3eff7fc55n9frc97nnPf5fFMaM6YecEqqHVyCn1Ot4CDcg38g1QhOwEsKUm3gQnwX+n+ozohOKt2NXaH9dZxUlREcj82heTc24NB4VocRnIcvQ+8vuKLr+WgbsTeV/gqt72HBFO1G1wiOxlNdqTR3mrajaQTn4ovQ9zuun6H96BnBndjZK5Wm6NPwEz7Hu3gGD+MOLJpuNvd1KmUewWF99u2HP/BCvKh57TtIe4Scg8+KVLphiJcxgbNwMVZgPd4oZlmUNM/nNqlFE3nqd8QAH+GM1oL/f5zDo7jchF8LU2/nSmGYwEfhySLgo3mwVtX3NrWsyAKhZWLQQHnqP9nTne24dZ+p7q1jLibxW2jZgsXVGSn0TODZ0PMnbqkitXpUEffF4ZuZHMnFPoCe66K6zoaWH5Dtty2wNIz8jSv394GYB92Gr/Ep3sfTeAC344I8xgB6VkXcrTh5IDMtlCgzkc2+g/vjwJwzQ9xc5mRezmtoNmYWF/eP/Jav7tPIAizEElwbJ/tDeBFfFQu5IV+Xs6nTe3wX+DHarhjYSAQ5Fs9FkCzgweZGOJ2RPrfZm/F4nBkNuyMNz5yiz43R5nscOcyWuKq4o7851Ye4fo109TkYl4WBXUUN9hiO69KQUzyzZlZGimDn45viqnv5sEa6+p+KJ/BvhPq2LChjPYka7YhhzUxEGS4GXIdD2jDSgLOLt5/T7d7i2Yfx/9vSsMQ0r47dJ/Ma5rdlJJPXYWwAzexsjDRcGX+/lWr6QIebio8eG+Ocy3Vh5rQ2B5qHV8u9tLXgAS4tzrTJ4ly5K7VJXiNY26RBq8GDXAkX5UqemcwrqcafFXQOVUU6b5+pKhjJH3p0bpQfl2mcv36mGsFFXUZmV7KMAjrFY8OGVCu4pjCyOdUK5kT5kvkg1Yy9O9iWVDO4KozsSDWDE5uiMtWOzqXvmAOtY8yYMWn/8B/TbS1rji7GgQAAAABJRU5ErkJggg==" class="back" on:click={goBack}>
  <div class="hero">
    <div class="hero-content">
      <h1 class="hero-title">BAPP</h1>
      <p class="hero-subtitle">I tuoi collegamenti</p>
      <textarea class="outputChat" id="outputChat" cols="30" rows="10" disabled bind:value={res}></textarea>
      <button class="hero-button" on:click={backToHome}>Torna alla home</button>
      
    </div>
  </div>

