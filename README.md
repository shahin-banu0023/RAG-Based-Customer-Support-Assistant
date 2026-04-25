# RAG-Based Customer Support Assistant

##  Project Objective

This project focuses on designing and building a **Retrieval-Augmented Generation (RAG)** based customer support assistant. The system is capable of:

* Processing a PDF knowledge base
* Retrieving relevant information using embeddings
* Answering user queries contextually
* Using a graph-based workflow for control logic
* Routing responses based on intent
* Supporting Human-in-the-Loop (HITL) escalation


## What is RAG?

Retrieval-Augmented Generation combines:

* **Retrieval** → Fetch relevant data from a knowledge base
* **Generation** → Generate answers using that context

## Core Pipeline

1. Load PDF
2. Chunk the text
3. Generate embeddings
4. Store in vector database (ChromaDB)
5. Retrieve relevant chunks
6. Generate response

## Workflow Design

* Graph-based execution using LangGraph
* Flow: **Input → Process → Output**
* Conditional routing based on intent

##  Data Flow

1. PDF → Text Extraction
2. Text → Chunking
3. Chunks → Embeddings
4. Embeddings → Stored in DB
5. Query → Retrieval
6. Retrieved Context → LLM
7. Response → Output / Escalation

## Technology Choices

* **ChromaDB** → Lightweight, fast vector DB
* **LangGraph** → Workflow orchestration
* **HuggingFace Embeddings** → Efficient and open-source
* **Python** → Flexible implementation

---

## Scalability Considerations

* Large PDFs → Efficient chunking
* High queries → Optimized retrieval
* Latency → Smaller embeddings + caching

## Conditional Routing Logic

| Condition     | Action     |
| ------------- | ---------- |
| Simple query  | RAG answer |
| Complex query | Escalate   |
| No context    | Escalate   |


## Error Handling

* Missing PDF text → Skip page
* No chunks found → Return fallback
* LLM failure → Escalate


RAG improves traditional AI by:

* Reducing hallucination
* Providing context-aware answers

Use case: Customer support automation
