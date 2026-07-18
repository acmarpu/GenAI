<div align="center">

## AI Pyramid

</div>

![alt text](https://github.com/acmarpu/images/blob/main/GenAI/02-image.png)

<br><br><br>

| Layer  | What it Means  | Examples|
|--------|----------------|---------|
| AI     | Any system that mimics human intelligence| spam filters thermostas, calculators |
| ML     | AI that learns patterns from data instead of hand-written rules | Netflix recommendations, fraud detection|
| DL     | ML using neural networks with many layers of pattern recognition  | Face unlock, voice assistants, image recognition |
| LLM    | Deep learning on text at massive scale (billions of parameters) | ChatGPT, Claude, Llama, Qwen  |

<br><br><br>

|  Level        |      Concept      | What the AI does |  What YOU do |  Example     |
|---------------|-------------------|------------------|--------------|--------------|
|   1           | Generative AI     | Writes when prompted |  Everything else --- find, read, paste, review, decide            |   ChatGPT basic chat   |
|   2           | + Tool Use        | Searches, reads URLs, Access files | Still Orchestrate the steps  | ChatGPT browsing |
|   3           | AI Agent           | Plans + executes the full workflow autonomouly | Give one instruction review the output  | A single agent script with think-act-observe loop|
|   4           |   Multi Agent     | Specialist agents, critic loops, revision pipelines | Give input, receive polished output | The resure tailor system (6 agents) |
|   5           | Full Autonomy     | Finds jobs, tailors, applies, preps - end to end | wake up with intervies | the version

<br><br><br>

<div align="center">

----------------------------------------------------------------------------------------------
## LLM
----------------------------------------------------------------------------------------------

</div>

* Self-Attention

* Next token prediction: LLM does every work by predicting the next token
  - GPT, Claude, LLAMA, Qwen - works in the way

* **How LLM works?**
<div align="center">
TEXT  ---------> TOKENS  ---------> ATTENTION ---------> PREDICT NEXT ---------> OUTPUT  
</div>

<br><br><br>

  

|  Frontier Models    | Open -Source LLMs    |
|---------------------|----------------------| 
|  ChatGpt            |  Llama               |
|  claude             |  Qwen                |
|  Gemini             |  Gemma               |
|                     |  Phi                 |
|                     |  Deepseek            |
|                     |                      |
|  Input Cost         |  No Cost             |
|  Output Cost        |  Data is ours [local]|
|  Token Cost         |                      |
|  Owned by others (companies) |             |
|  Pay per use         |                     |
|  Data goes to servers|                     |
|                      |                     |
|  Data goes to servers| Fine tuned the models on your data |
|  cannot change the behavior of model|                     |

<br><br><br>

----------------------------------------------------------------------------------------------
#### Tokens: "Chunks of data"
----------------------------------------------------------------------------------------------

|   Token  |  Tokenizer  |   Tokenization |
|----------|-------------|----------------|
| the small piece of a word | this is the one which does the process | is a process of bulding the tokens |

<br><br><br>

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

<br><br><br>

    |  h  | e   |  l  | l   |  o  |
    |-----|-----|-----|-----|-----|
    | 104 | 101 | 108 | 108 | 111 |

<br><br><br>

----------------------------------------------------------------------------------------------
#### Tokenization:
----------------------------------------------------------------------------------------------

* **Step 1:** Understand the Input (**Tokenization**)
* Text broken into smaller units called tokens, each mapped to a numeric ID.
* "Artificial intelligence is transforming" becomes [2987,9231,318...].
* The model never sees your words, only token IDs, This is why token count drives both your cost and your context limit. Every character you type is converted to currency before the mocel even starts working.

  - Tokens can be words, characters, or sub-words
  - Makes text easier for models to understand and process
  - Helps convert unstructured text into a structured format
  - Used in most NLP tasks like classification, translation and search

* **ASCII** : is a numbering system
  - ASCII (American Standard Code for Information Interchange) is a standard numbering system that assigns a unique number to each character.
  - Why Isn't ASCII Enough for LLMs?
  - ASCII simply assigns a number to each individual character.
  - It doesn't understand words or their meanings.

* **Step 2:** Convert Tokens into Context(**Embeddings:**)
*  it is a way to convert your each token into a vector or numerical representation an embedding layer.
  - Once the text is tokenized, each token is converted into a vector (a list of numbers) This process is called embedding.
  - An embedding captures the meaning of a token, not just its identity.
  - Embedding is a vector of numbers that represents the token's meaning and its relationship to other tokens, enabling the model to perform mathematical operations on language.
  
* **Step 3:** Find What's Important (Attention)
* Queries ask questions. Keys store information. Values hold the details.
* The breakthrough that made modern LLMs possible. Every word weighed against every other word simultaneously. "It" knows what it refers to because attention connects them directly no matter how far apart they are.


* **Step 4:** Process and Refine (**Transformer Blocks**)
* Multi-head attention plus feed-forward networks, wrapped in Add and Norm with skip connections.
* This block repeats across L layers: 12, 24, 48, and beyond.
* Depth is where capability comes from. Early layers catch syntax. Middle layers capture meaning. Deep layers handle reasoning. Stacking layers is largely why a bigger model "understands" more than a small one.
* **Transformers:** 
  - The Transformer is the neural network architecture that processes embeddings and determines how the tokens relate to each other.


* **Step 5:** Predict the Next Word (**Generation**)
The model outputs probabilities for the next token: data 0.31, people 0.21, better 0.15...
It picks one, appends it, and repeats, one token at a time until it hits an end token.
An LLM isn't "thinking out" a full answer. It's predicting the next token, over and over, fast enough to look like thought. That single fact explains hallucinations (confident but wrong predictions), streaming (tokens arriving one by one), and why output tokens cost more (each one requires a full forward pass).


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

  |  Without Memory           |  With Memory                  |
  |---------------------------|-------------------------------|
  | Each cell is a fresh start| Each cell is not a fresh start |
  | we dont send any history  | We will send entire AI Conversation history every AI chat (every time). |
  | the model does not have anything to read | the model reads all of it and responds in its context |

* Refer 02_LLM_Induction_practic.ipynb for memory and without memory code

<br><br><br>

#### OLLAMA Introduction
* Ollama is an Open-source platform to download, install, manage, run, and deploy large language models[LLMs]. 
* All this can be done locally with Ollama

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



