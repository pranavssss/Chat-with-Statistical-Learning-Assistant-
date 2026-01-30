# Statistical Learning Conversational Assistant  
**Chat with _An Introduction to Statistical Learning with Applications in Python_**

This project implements a **conversational AI assistant** that can answer questions directly from the book  
_An Introduction to Statistical Learning with Applications in Python_ using **Retrieval-Augmented Generation (RAG)**.

The system ingests the unstructured PDF of the book, processes and indexes its content, and enables users to interact with it via a **Flask-based web interface**, powered by **Azure AI Foundry**, **Azure Cognitive Search**, and **GPT-4o**.

---

## Project Overview

The goal of this project is to build a domain-specific chatbot capable of:
- Understanding questions related to statistical learning concepts
- Retrieving relevant context from the book
- Generating accurate, grounded answers using LLMs

The assistant behaves like a **Statistical Learning tutor**, responding conversationally while staying faithful to the source material.

---

## System Architecture

1. **Data Source**
   - PDF: *An Introduction to Statistical Learning with Applications in Python*
   - Stored in **Azure Blob Storage**
   - Accessed securely using a **Shared Access Signature (SAS) token**

2. **Document Processing**
   - PDF content extracted and cleaned
   - Text **chunked** into manageable segments
   - Metadata preserved for traceability

3. **Indexing & Search**
   - Indexed using **Azure Cognitive Search**
   - **Hybrid Search** approach:
     - Keyword-based search
     - Semantic / vector search using embeddings
   - Improves recall and relevance for complex queries

4. **Retrieval-Augmented Generation (RAG)**
   - Relevant chunks retrieved from the search index
   - Context injected into prompts
   - **GPT-4o** used for grounded text generation

5. **Model & Orchestration**
   - Experimented and validated using **Azure AI Foundry Playground**
   - Configured endpoints and subscription keys for production use

6. **Web Application**
   - Built with **Flask**
   - Simple chat UI connected to Azure endpoints
   - Handles user input, retrieval, and response rendering

---

##  Technologies Used

### Cloud & AI
- **Azure AI Foundry** – Model experimentation and prompt testing
- **Azure OpenAI (GPT-4o)** – Natural language generation
- **Azure Cognitive Search** – Hybrid (keyword + semantic) retrieval
- **Azure Blob Storage** – PDF storage
- **Shared Access Signature (SAS)** – Secure blob access

### Backend
- **Python**
- **Flask** – Web server and API handling
- **REST APIs** – Azure service integration

### NLP & Search
- Document chunking & preprocessing
- Embedding-based vector search
- Retrieval-Augmented Generation (RAG)

---

##  Project Stages

### 1. Data Ingestion
- Upload PDF to Azure Blob Storage
- Generate SAS token for controlled access

### 2. Preprocessing & Chunking
- Extract text from PDF 
- Split content into overlapping chunks
- Prepare data for indexing

### 3. Index Creation
- Create Azure Cognitive Search index
- Store text chunks, embeddings, and metadata

### 4. Hybrid Retrieval
- Combine keyword search with semantic vector search
- Retrieve the most relevant sections per query

### 5. LLM Integration
- Pass retrieved context to GPT-4o
- Generate accurate, book-grounded responses based on the queries

### 6. Web Interface
- Flask-based chat UI
- Communicates with Azure endpoints using subscription keys
- Displays conversational responses to users


---

##  Use Cases

- Learning and revising statistical learning concepts
- Quick reference for ML models and theory
- Educational RAG chatbot implementation example
- Azure-based LLM application development




