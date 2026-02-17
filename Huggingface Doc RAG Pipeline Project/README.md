# RAG Pipeline with Milvus, Sentence Transformers, and Qwen

## 📌 Project Overview

This project implements an end‑to‑end **Retrieval‑Augmented Generation
(RAG)** pipeline using:

-   Sentence Transformers for embeddings
-   Milvus as a vector database
-   Hugging Face Transformers for LLM generation (Qwen)
-   Python for orchestration

The system retrieves relevant document chunks using semantic search and
generates grounded answers using a large language model.

------------------------------------------------------------------------

## 🏗️ Architecture

1.  Document Chunking → Split documents into overlapping chunks\
2.  Embedding Generation → Convert text chunks into vector embeddings\
3.  Vector Storage → Store embeddings in Milvus\
4.  Retrieval → Fetch top‑k relevant chunks\
5.  Generation → Generate answer using retrieved context

------------------------------------------------------------------------

## 📂 Project Structure

    .
    ├── chunking.py
    ├── embeddings.py
    ├── milvus_insert.py
    ├── retrieval.py
    ├── generation.py
    ├── main.ipynb / main.py
    └── README.md

------------------------------------------------------------------------

## ⚙️ Installation

### 1️⃣ Clone repository

    git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
    cd YOUR_REPO

### 2️⃣ Create virtual environment

    python -m venv venv
    source venv/bin/activate   # Linux/Mac
    venv\Scripts\activate      # Windows

### 3️⃣ Install dependencies

    pip install -r requirements.txt

------------------------------------------------------------------------

## 📦 Requirements

-   Python 3.9+
-   transformers
-   sentence-transformers
-   pymilvus
-   torch
-   accelerate
-   bitsandbytes (optional)

------------------------------------------------------------------------

## 🚀 Usage

### Step 1 --- Prepare documents

Load documents into list of dictionaries:

    documents = [
        {"text": "...", "source": "file1"},
    ]

### Step 2 --- Chunk documents

    chunks = chunk_all_documents(documents)

### Step 3 --- Generate embeddings

    embeddings = generate_embeddings(texts, model)

### Step 4 --- Insert into Milvus

    insert_data_to_milvus(client, collection_name, chunks, embeddings)

### Step 5 --- Retrieve

    docs = retrieve_documents(query, client, collection_name, embedding_model)

### Step 6 --- Generate answer

    result = generate_answer(query, docs, generator)

------------------------------------------------------------------------

## 🧠 Prompt Strategy

The model is instructed to answer ONLY from context to reduce
hallucinations.

------------------------------------------------------------------------

## 📊 Features

✅ Overlapping chunking\
✅ Batch embedding generation\
✅ Vector similarity search\
✅ Context‑aware answer generation\
✅ Modular pipeline\
✅ Production‑ready structure

------------------------------------------------------------------------

## 🔮 Future Improvements

-   Hybrid search (BM25 + Vector)
-   Cross‑encoder reranking
-   Streaming responses
-   Evaluation metrics
-   API deployment with FastAPI
-   UI with Streamlit

------------------------------------------------------------------------

## 🛠️ Tech Stack

-   Python
-   Hugging Face Transformers
-   Sentence Transformers
-   Milvus
-   PyTorch

------------------------------------------------------------------------

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss.

------------------------------------------------------------------------

## 📜 License

MIT License

------------------------------------------------------------------------

## 👤 Author

Peetha Raghavendra\
Machine Learning Engineer

------------------------------------------------------------------------

⭐ If you found this useful, please star the repo!
