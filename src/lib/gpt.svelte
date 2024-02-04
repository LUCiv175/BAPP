<script>
  
    let mymessage = '';
    
    import OpenAI from "openai";
    export let allchat = [];
  
    const openai = new OpenAI({
      apiKey: '',
      dangerouslyAllowBrowser: true
    });
    
    export const btnsend = async () => {
      try {
        const userMessage = mymessage;
        if (userMessage !== '') {
          // Add user message to the chat
          allchat = [...allchat, { role: 'user', text: userMessage }];
          
          const response = await openai.chat.completions.create({
            messages: [{ role: 'system', content: userMessage }],
            model: 'gpt-3.5-turbo',
          });
  
          // Add chatbot message to the chat
          const chatbotMessage = response.choices[0].message.content;
          allchat = [...allchat, { type: 'chatBot', text: chatbotMessage }];
  
          // Clear the input field
          mymessage = '';
        }
      } catch (err) {
        console.error(err);
      }
    };
  </script>
  
  <style>
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
  <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADIAAAAyCAYAAAAeP4ixAAAACXBIWXMAAAsTAAALEwEAmpwYAAADKElEQVR4nO3ZX+jfUxzH8YMZIsKPNcQuuOCG2Vy4wZJ/hcjfYtqS1UrUfhfaUnax5AJtabVEKXfKn9QQSpT/4kYSIuY/m9TYDHvo7Pv+tOPb7/f9fb+/72fb99T3eff7fc55n9frc97nnPf5fFMaM6YecEqqHVyCn1Ot4CDcg38g1QhOwEsKUm3gQnwX+n+ozohOKt2NXaH9dZxUlREcj82heTc24NB4VocRnIcvQ+8vuKLr+WgbsTeV/gqt72HBFO1G1wiOxlNdqTR3mrajaQTn4ovQ9zuun6H96BnBndjZK5Wm6NPwEz7Hu3gGD+MOLJpuNvd1KmUewWF99u2HP/BCvKh57TtIe4Scg8+KVLphiJcxgbNwMVZgPd4oZlmUNM/nNqlFE3nqd8QAH+GM1oL/f5zDo7jchF8LU2/nSmGYwEfhySLgo3mwVtX3NrWsyAKhZWLQQHnqP9nTne24dZ+p7q1jLibxW2jZgsXVGSn0TODZ0PMnbqkitXpUEffF4ZuZHMnFPoCe66K6zoaWH5Dtty2wNIz8jSv394GYB92Gr/Ep3sfTeAC344I8xgB6VkXcrTh5IDMtlCgzkc2+g/vjwJwzQ9xc5mRezmtoNmYWF/eP/Jav7tPIAizEElwbJ/tDeBFfFQu5IV+Xs6nTe3wX+DHarhjYSAQ5Fs9FkCzgweZGOJ2RPrfZm/F4nBkNuyMNz5yiz43R5nscOcyWuKq4o7851Ye4fo109TkYl4WBXUUN9hiO69KQUzyzZlZGimDn45viqnv5sEa6+p+KJ/BvhPq2LChjPYka7YhhzUxEGS4GXIdD2jDSgLOLt5/T7d7i2Yfx/9vSsMQ0r47dJ/Ma5rdlJJPXYWwAzexsjDRcGX+/lWr6QIebio8eG+Ocy3Vh5rQ2B5qHV8u9tLXgAS4tzrTJ4ly5K7VJXiNY26RBq8GDXAkX5UqemcwrqcafFXQOVUU6b5+pKhjJH3p0bpQfl2mcv36mGsFFXUZmV7KMAjrFY8OGVCu4pjCyOdUK5kT5kvkg1Yy9O9iWVDO4KozsSDWDE5uiMtWOzqXvmAOtY8yYMWn/8B/TbS1rji7GgQAAAABJRU5ErkJggg==" class="back">
  
    <div class="hero">
      <div class="hero-content">
        <h1 class="hero-title">BAPP</h1>
        <p class="hero-subtitle">Inserisci il materiale e genera i collegamenti</p>
        <input type="text" class="input-text" bind:value={mymessage} placeholder="Inserisci lo stimolo"><br>
        <button class="hero-button" on:click={btnsend}>Genera</button>
      </div>
    </div>
  
  
