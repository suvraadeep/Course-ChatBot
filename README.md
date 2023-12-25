# Course-ChatBot using Llama-2 7B model

This chatbot is meant to answer all your questions related to BT203, BT204, BT204, trained using all the textbooks of the respective textbooks.


# Architecture 
1. Extracted dats Books PDF
2. Divided into text Chunks (750 in this case)
3. Using Embeedings
4. Results stored
5. Final Results using Llama 2 7B model (Y'll can use any model of your choice of any number of parameters)
(6. Deployment using Streamlit or Flask)
src="https://github.com/suvraadeep/Course-ChatBot-using-Llama-2-7B-model-and-Gemini-Pro/assets/154406386/45d4efa0-dbb5-484e-8a94-5891e762c83c">


# Update 25/12/2023

Implemented the same thing using Google-Gemini-Pro-API which you can find in `Course-ChatBot-using-Gemini-Pro.ipynb` file.
But Before everything let me drop some notes
1. For embedding model in this case I implemented a google embeddings model `embedding-001`  unlike last time as we used a hugging face embedding model
2. For Vector Database I used Chroma this time but few things to note again, Chroma is efficient for many use cases, it might not match Pinecone’s performance in certain high-throughput real-time scenarios as Pinecone excels at similarity search. ChromaDB is an open-source database that you need to set up and manage yourself. This can be a significant hurdle for users who don't have experience with database administration or who require a plug-and-play solution. Pinecone, on the other hand, is a managed service that takes care of all the infrastructure and maintenance, making it much easier to get started. However, if you're comfortable with managing your own infrastructure, appreciate the flexibility of open-source software, and have budget constraints, ChromaDB could be a viable option.

# NOTE!!!
1. This model is Trained To run over Local CPU hence it might take some time (<2 min definetely) to get response.
2. Also as I mentioned you can use any model of any number of parameter but do keep in mind that Larger size means smarter, but slower.
3. I set the temperature value to 0.8. Now what's Temperature? Adjusts randomness of outputs, greater than 1 is random and 0 is deterministic to the point, 0.75 is a good starting value hence I used 0.8.
4. Also you can change the number of tokens, a word is generally 2-3 tokens.
5. In the `Line 23` of `app.py` change the `index_name` based upon your `index_name`.
6. I used some randomly AI generated HTML CSS code So I dont take credit for this (Also dont judge me for this :)

![WhatsApp Image 2023-12-24 at 22 41 01_3fb144cf](https://github.com/suvraadeep/Course-ChatBot/assets/154406386/d3c06db2-9f2a-4b16-b48d-13c2b9adcd7a)

# Now after all these How to Run?

### STEPS:

Clone the repository

```bash
Run This Over your terminal : git clone https://github.com/suvraadeep/Course-ChatBot.git
```
### STEP 01- Create an environment after cloning and run the same over your terminal
Change the python version based upon the version over your PC

```bash
conda create -n chatbot python=3.10.9 -y
```

```bash
conda activate chatbot
```

### STEP 02- install the Libraries
We will download all the Libs required altogether
```bash
pip install -r requirements.txt
```

### Note: The book I used is stored in `Books` folder

### Step 03- Create a `.env` file in the root directory and add all your credentials as follows:
We will use Pinecone database for this project but again you can use ChromaDB or any database of your choice
You need to generate it yourself 
```ini
PINECONE_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
PINECONE_API_ENV = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

### Step 04- Download the quantized model from the link provided below.


```ini
## Download the Llama 2 Model:

The model I used is llama-2-7b-chat.ggmlv3.q8_0.bin
## From the following link:
https://huggingface.co/TheBloke/Llama-2-7B-Chat-GGML/tree/main

## For other parameter models you can use
## 13B Quantized model
https://huggingface.co/TheBloke/Llama-2-13B-chat-GGML

## You can also use up the model originally from mets site using
https://ai.meta.com/llama/

```
### STEP 05- Run `helper.py`, `prompt.py`, `setup.py`, `store_index.py`
```bash
# Finally run the following file 
app.py

```
### Step 06- Running it Locally  
```bash
# Finally paste it over your browser
localhost:8069
```
cheers ;)





