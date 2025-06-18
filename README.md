# 🎙️ RAG-based YouTube Chatbot with Hugging Face & LangChain

This repository contains a Retrieval-Augmented Generation (RAG) chatbot that answers questions based on transcripts of YouTube videos. It combines the power of vector search and Hugging Face LLMs to produce relevant, contextual answers.

---

## 📌 Features

- ✅ Automatically fetches and processes YouTube video transcripts.
- ✅ Splits and embeds text using Hugging Face embeddings.
- ✅ Stores embeddings in a FAISS vector database.
- ✅ Performs semantic search to retrieve relevant chunks.
- ✅ Uses Hugging Face-hosted LLMs (e.g., LLaMA-3 or Zephyr) for response generation.
- ✅ End-to-end pipeline based on LangChain.

---

## 🧠 Architecture

Below is the architecture flowchart of the RAG-based pipeline:

![Flowchart](cce08112-a29a-4834-967c-dee780d21f15.png)

---

## 🔁 Workflow

1. **Document Loading**  
   Transcript is fetched using `youtube-transcript-api`.

2. **Text Splitting**  
   The transcript is split into manageable chunks using `RecursiveCharacterTextSplitter`.

3. **Embedding Generation**  
   Text chunks are converted into embeddings using a Hugging Face embedding model (`HuggingFaceEmbeddings`).

4. **Vector Store Creation**  
   Embeddings are stored in a FAISS vector store for fast similarity search.

5. **Retrieval**  
   Given a user query, the top-k most relevant chunks are retrieved via semantic search.

6. **Prompt Construction**  
   The query and retrieved chunks are combined into a prompt.

7. **Response Generation**  
   Prompt is passed to a Hugging Face-hosted LLM (e.g., `meta-llama/Meta-Llama-3-8B-Instruct` or `HuggingFaceH4/zephyr-7b-beta`) to generate a response.

---

## 🚀 Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/Abhishek603124/YouTube_ChatBot.git
   cd YouTube_ChatBot
