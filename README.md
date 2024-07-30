# QA_RAG__Llma2_7B

# Conversational Retrieval-augmented generation (RAG) with Hugging Face, LangChain with FAISS 

This project demonstrates the implementation of a conversational retrieval system using Hugging Face transformers and LangChain. The system loads a large language model (meta-llama/Llama-2-7b-chat-hf), ingests documents from web links, processes them into chunks, creates embeddings, and sets up a retrieval chain to answer queries based on the ingested documents.

## Features

- Load and configure a large language model with 4-bit quantization.
- Ingest documents from specified web links.
- Split documents into manageable chunks.
- Create embeddings using the `sentence-transformers/all-mpnet-base-v2` model.
- Store embeddings in a FAISS vector store for efficient retrieval.
- Implement a conversational retrieval chain to answer queries based on the stored document embeddings.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/your-repo-name.git
    ```
2. Navigate to the project directory:
    ```bash
    cd your-repo-name
    ```
3. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

1. Load the Hugging Face model and set up the text generation pipeline.
2. Ingest documents from the provided web links using the `WebBaseLoader`.
3. Split the documents into chunks using `RecursiveCharacterTextSplitter`.
4. Create embeddings and store them in a FAISS vector store.
5. Initialize and use the `ConversationalRetrievalChain` to answer queries.

## Example Queries

```python
query = "What is Data lakehouse architecture in Databricks?"
result = chain({"question": query, "chat_history": []})
print(result['answer'])

