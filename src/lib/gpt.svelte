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
    /* Your styles here */
  </style>
  
  <div id="chatDiv">
    {#each allchat as res_msg}
      <div class="message {res_msg.type}">
        <span class="whosend">
          {res_msg.type === 'user' ? 'You' : 'chatBot'}
        </span>
        {res_msg.text}
      </div>
    {/each}
  </div>
  
  <div>
    <input type="text" bind:value={mymessage}>
    <button type="button" on:click={btnsend}>Send</button>
  </div>
  