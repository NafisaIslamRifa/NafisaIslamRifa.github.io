---
title: "Agentic RAG London Tube Assistant"
collection: teaching
type: "Applied AI / Agentic RAG / LLM Tool Calling"
permalink: /teaching/2026-agentic-rag-london-tube-assistant
venue: "Personal AI Project"
date: 2026-10-07
location: "London, United Kingdom"
---

Built an agentic RAG assistant for London transport. An LLM agent chooses between live Transport for London (TfL) data and official TfL guidance to answer questions about line status, next trains, fares, paying, refunds, discounts and accessibility, with cited answers and guardrails enforced in code. The project was rebuilt from an earlier prototype into a tested, containerised and publicly deployed application.

## Key Contributions

- Built an **LLM agent** with four real TfL tools for guidance, live line status, arrivals, and fares, supporting multi-tool and follow-up queries.
- Developed a **RAG pipeline** over 11 official TfL pages using section-aware chunking, BGE embeddings, and Chroma (**140 chunks**).
- Achieved **97% Top-3 section retrieval accuracy** and **100% Top-5 page accuracy** across 32 evaluation questions.
- Compared vector search with a cross-encoder reranker and selected **vector search as the default** based on accuracy and latency.
- Integrated the **TfL Unified API** with retries and typo-tolerant station search.
- Added **guardrails** to prevent unsupported links, invented fares, excessive searches, and token overuse.
- Made the system **LLM-provider agnostic**, supporting Groq, Ollama, and OpenAI-compatible APIs.
- Built a **Streamlit interface** with chat, sources, answer steps, live status, fares, and arrivals.
- Added **90+ automated tests, Docker/Compose, health checks, and GitHub Actions CI/CD** for reliability.
## Project Links

- [GitHub Repository](https://github.com/NafisaIslamRifa/london-tube-assistant)
- [Live Demo](https://london-tube-assistant.streamlit.app/)

## Technologies Used

- Python
- LLM tool calling (OpenAI-compatible API: Groq gpt-oss-120b, Ollama Llama 3.2)
- Retrieval-Augmented Generation (RAG)
- ChromaDB
- fastembed (BAAI/bge-small-en-v1.5), cross-encoder reranking (evaluated)
- Transport for London (TfL) Unified API
- Streamlit
- Docker and Docker Compose
- GitHub Actions (CI)
- pytest
