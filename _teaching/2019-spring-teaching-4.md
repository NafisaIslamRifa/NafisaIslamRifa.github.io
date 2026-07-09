---
title: "AGENTIC AI-POWERED LONDON TUBE ASSISTANT USING RETRIEVAL-AUGMENTED GENERATION (RAG)"
collection: teaching
type: "Applied AI / Retrieval-Augmented Generation (RAG)"
permalink: /teaching/2026-agentic-rag-london-tube-assistant
venue: "Personal AI Project"
date: 2026-07-01
location: "London, United Kingdom"
---

Developed an intelligent London Tube Assistant that combines Retrieval-Augmented Generation (RAG), agentic AI routing, and live Transport for London (TfL) APIs to answer both static transport questions and real-time travel queries.

## Key Contributions

- Built a Retrieval-Augmented Generation (RAG) pipeline using official TfL documents for grounded question answering.
- Implemented semantic retrieval using sentence-transformer embeddings with ChromaDB as the vector database.
- Improved retrieval quality by integrating a cross-encoder reranker before response generation.
- Integrated a local Ollama Llama 3.2 model to generate context-aware answers from retrieved documents.
- Developed an agentic routing layer that automatically dispatches user queries to the appropriate tool (RAG, live APIs, or map retrieval).
- Integrated live TfL APIs to provide real-time line status, fare calculation, and train arrival predictions.
- Designed an interactive Streamlit web application with support for intelligent Q&A, fare estimation, live transport updates, and Tube map retrieval.

## Project Links

- [GitHub Repository](https://github.com/your-username/your-repository)
- [YouTube Demo](https://www.youtube.com/watch?v=m0-3QXqZvxA)

## Technologies Used

- Python
- Streamlit
- LangChain
- ChromaDB
- Ollama (Llama 3.2)
- Sentence-Transformers
- Cross-Encoder Reranking
- Transport for London (TfL) Unified API
- Retrieval-Augmented Generation (RAG)
- Agentic AI
