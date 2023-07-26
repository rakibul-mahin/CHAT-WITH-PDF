# CHAT-WITH-PDF

In this jupyter notebook you can use your PDF and ask questions from that PDF and it will generate answers for you from that PDF. Here I have used method that is completely free by using HuggingFace. However, if you want better results then you can try using OpenAI but that requires credit.

## Instructions on using the Jupyter Notebook

1. First clone this repository.
2. Create a folder named `files` and inside that _file_ folder create another folder named `Documents` and keep your PDF inside _Documents_ folder.
3. Then get your API key from HuggingFace or OpenAI and paste it (any one, in this notebook I tried with HF key only to use OpenAI API key you need to change some codes):
   - `os.environ["OPENAI_API_KEY"] = "Your_OpenAI_API_Key_Here"`
   - `os.environ["HUGGINGFACEHUB_API_TOKEN"] = ""Your_HF_API_Key_Here`
4. Write your questions on `query = 'Your Question?'` and run all the cells. **Note: Using HuggingFace might take some time for embedding**
5. Done!!!

## Different LLMs

If you want to try different models then change the code below

```py
qa_chain_instrucEmbed = RetrievalQA.from_chain_type(
    llm=HuggingFaceHub(
        repo_id="YOUR_MODEL_REPO_NAME",
        model_kwargs={"temperature":0.5,"max_length":1000}
    ),
    chain_type="stuff",
    retriever=retriever,
    return_source_documents=True
)
```

## Thank You

If you find any issues feel free to contact me
