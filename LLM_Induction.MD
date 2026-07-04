<div align="center">

## AI Pyramid

</div>


![alt text](https://github.com/acmarpu/images/blob/main/GenAI/02-image.png)


|  Level        |      Concept      | What the AI does |  What YOU do |  Example     |
|---------------|-------------------|------------------|--------------|--------------|
|   1           | Generative AI     | Writes when prompted |  Everything else --- find, read, paste, review, decide            |   ChatGPT basic chat   |
|   2           | + Tool Use        | Searches, reads URLs, Access files | Still Orchestrate the steps  | ChatGPT browsing |
|   3           | AI Agent           | Plans + executes the full workflow autonomouly | Give one instruction review the output  | A single agent script with think-act-observe loop|
|   4           |   Multi Agent     | Specialist agents, critic loops, revision pipelines | Give input, receive polished output | The resure tailor system (6 agents) |
|   5           | Full Autonomy     | Finds jobs, tailors, applies, preps - end to end | wake up with intervies | the version
     

<div align="center">

## LLM

</div>

* self -Attention

* Next token prediction: LLM does every work by predicting the next token
  - GPT, Claude, LLAMA, Qwen - works in the way

* How LLM works?

<div align="center">

TEXT  ---------> TOKENS  ---------> ATTENTION ---------> PREDICT NEXT ---------> OUTPUT  

</div>


#### Tokens: "Chunks of data"
* A token is a small piece of text the model reads before it runs that piece into a number.
* The model doesn't read whole sentences or words directly. Instead, it first breaks the text into smaller pieces called tokens and then converts each token into a number (called a token ID) that the model can understand.

* **Why are Tokens Needed?**
  - Computers don't understand English (or any human language).
  - They only understand numbers.
  - So before an LLM can process your prompt:
  - Create an Azure Resource Group
  - it first converts the text into tokens and then into numbers.
  
  |                                  |         |
  |----------------------------------|---------| 
  |  Your Prompt                     |         |
  |    │                             |         |
  |    ▼                             |         |
  |  Break into Tokens               |         |
  |    │                             |         |
  |    ▼                             |         |
  |  Convert Tokens into Numbers     |         |
  |    │                             |         |
  |    ▼                             |         |
  |  LLM Processes the Numbers       |         |
  |    │                             |         |
  |    ▼                             |         |
  |  Generate Response               |         |


* **ASCII** : is a numbering system
  - ASCII (American Standard Code for Information Interchange) is a standard numbering system that assigns a unique number to each character.

  - Why Isn't ASCII Enough for LLMs?
    - ASCII simply assigns a number to each individual character.
    - It doesn't understand words or their meanings.

    |  h  | e   |  l  | l   |  o  |
    |-----|-----|-----|-----|-----|
    | 104 | 101 | 108 | 108 | 111 |


#### **Tokenization:**
* Tokenization is the process of breaking text into smaller pieces called tokens.which helps machines process and analyze language effectively.

  - Tokens can be words, characters, or sub-words
  - Makes text easier for models to understand and process
  - Helps convert unstructured text into a structured format
  - Used in most NLP tasks like classification, translation and search


* **Embeddings:** it is a way to convert your token into a vector or numerical representation
  - Once the text is tokenized, each token is converted into a vector (a list of numbers) This process is called embedding.
  - An embedding captures the meaning of a token, not just its identity.
  - Embedding is a vector of numbers that represents the token's meaning and its relationship to other tokens, enabling the model to perform mathematical operations on language.

* **Transformers:** 
  - The Transformer is the neural network architecture that processes embeddings and determines how the tokens relate to each other.


- Token ID = Identity
- Embedding = Meaningful description in numerical form


* **Token per second (TPS):** 
  - How fast the model writes its answer
  - Tokens Per Second (TPS) measures how quickly an LLM generates output.
  - what is the capability of the LLM model to generate how many number of tokens that it can generate in a second?.
  -  how fast deside - based on your complexity of the question, based on the server's busyness, based on the prompt that you provide, based on the thinking model reasoning capacity all these your output will depend on TPS.

* **Context Windows:** The model's working memory limit 
  - The Context Window is the maximum amount of text (measured in tokens) that an LLM can consider at one time.

  - You can think of it as the model's working memory during a conversation.






  #### OLLAMA Introduction
* Ollama is an Open-source platform to download, install, manage, run, and deploy large language models[LLMs]. 
* All this can be done locally with Ollama

* LLM stands for **Large language Model.** These Models are designed to understand, generate and interpret human language at a high level.

* Here are some key points about LLMs.

  - Typically contains billions of parameters, allowing them to grasp complex language patterns and generate cherent text.
  - Trained on vast datasets that include books, articles, websites, and other text sources.
  - Can perform tasks like text generation, summarization, translation, and answering questions.

* The following are some features of Ollama
  - **Model Library**: Offers a varity of pre-built models like Llama , Mistra, etc.
  - **Customization**: Allows you to customize and create your own models.
  - **Easy**: Provides a simple API for creating, running, and managing models
  - **Cross-Platform**: Available for macOS, Linux, and Windows
  - **Modelfile**: Packages everything you need to run an LLM into a single Modelfile, making it easy to manage and run models 

  |       |                       |         |
  |-------|-----------------------|---------|
  |       |                       | llama   |
  |       |                       | Gemma   |
  | System|     Ollama Locally    | Mistral |
  |       |                       |  Phi    |
  |       |                       | Qwen    |



