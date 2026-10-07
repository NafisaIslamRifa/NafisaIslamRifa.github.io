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

- Designed an LLM agent with real tool calling across four tools: TfL guidance search, live line status, live arrivals and live fares. The model chooses tools itself, can combine several in one answer (e.g. a fare and a line's status), and handles follow-up questions.
- Built a retrieval pipeline over 11 official tfl.gov.uk pages: cleaning that removes cookie banners and navigation, section-aware chunking so each answer can cite an exact page section, BGE embeddings via fastembed (ONNX, no PyTorch) and a Chroma vector store (140 chunks).
- Evaluated retrieval on 32 everyday-language questions mapped to the TfL section that answers them: right section in the top 3 for 97% of questions, and right page in the top 5 for all of them.
- Measured a cross-encoder reranker against plain vector search. It lowered section-level Hit@1 (0.81 → 0.78) while adding latency, so vector search became the default and reranking a configuration option.
- Used evaluation to find and fix real problems: moved TfL pages, test questions that expected headings TfL no longer uses, and hosting servers being blocked from scraping tfl.gov.uk (fixed by shipping a dated snapshot of the pages).
- Integrated the TfL Unified API with retries and a station directory built from TfL's own data, which tolerates typos ("picadilly circus") and partial names ("kings cross").
- Added guardrails in code: every link in an answer is checked against tool results, unknown stations produce suggestions instead of invented fares, and limits on steps and searches keep usage within free-tier token budgets.
- Made the LLM provider-agnostic: free hosted gpt-oss-120b on Groq, a local Llama 3.2 through Ollama, or any OpenAI-compatible API, switched by configuration only, with client-side rate limiting and retries.
- Built a Streamlit app with a chat assistant (sources and a step-by-step "How I answered" panel), a live line-status board, a fare finder and live next trains.
- Engineered for reliability: 90+ offline unit tests (scripted fake LLM, saved TfL replies, Streamlit UI tests), a Docker image with a health check, Docker Compose with an optional local Ollama container, and a GitHub Actions pipeline that runs the tests, then builds and health-checks the image.

## Project Links

- [GitHub Repository](https://github.com/NafisaIslamRifa/london-tube-assistant)
- [Live Demo](https://YOUR-APP.streamlit.app)

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
