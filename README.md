LangChain: A Customer Support Chatbot
=====================================

LangChain is a customer support chatbot that uses OpenAI's GPT-3.5-turbo model to answer questions based on a set of documents. It uses a variety of tools and techniques to load, split, and embed documents into a vector store, and then retrieve relevant information to answer user queries.

How it Works
------------

1.  Document Loading: LangChain uses the `SeleniumURLLoader` to load documents from a list of URLs. These documents are web articles that the chatbot will use to answer questions.

2.  Text Splitting: The loaded documents are split into smaller chunks using the `CharacterTextSplitter`. This makes it easier to handle and process the text.

3.  Embedding: Each chunk of text is then embedded using the `OpenAIEmbeddings` class. This transforms the text into a numerical representation that can be used for similarity search.

4.  Vector Store Creation: The embeddings are stored in a `DeepLake` dataset. DeepLake is a vector store that allows efficient similarity search.

5.  Question Answering: When a question is asked, LangChain retrieves the most relevant chunks from the DeepLake dataset using a similarity search. It then uses the GPT-3.5-turbo model to generate an answer based on these chunks.

Usage
-----

To use LangChain, you need to have your OpenAI API key saved in the `OPENAI_API_KEY` environment variable. You also need to replace `my_activeloop_org_id` and `my_activeloop_dataset_name` with your own organization ID and dataset name.

Once you have set up these details, you can ask LangChain a question by calling the `OpenAI` class with your question and the formatted prompt.

Example
-------

In the provided example, LangChain is asked "How to check disk usage in Linux?". It retrieves relevant chunks from the DeepLake dataset, formats the prompt, and generates an answer using the GPT-3.5-turbo model.

Note
----

LangChain is a powerful tool for customer support, but it should be used responsibly. It should only use information from the provided context and should not invent information. It should also handle sensitive information carefully and respect user privacy
