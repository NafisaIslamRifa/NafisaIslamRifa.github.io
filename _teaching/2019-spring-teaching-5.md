---
title: "UKNest: Agentic RAG Assistant for UK Newcomers"
collection: teaching
type: "Applied AI / Agentic RAG / MCP"
permalink: /teaching/2026-uknest-uk-newcomer-assistant
venue: "Personal AI Project"
date: 2026-10-01
location: "London, United Kingdom"
---

Developed UKNest, an AI assistant that helps people who have recently moved to the UK understand everyday rules such as right to work, eVisas and share codes, renting and deposits, council tax, and NHS access. It answers only from official GOV.UK guidance, cites the exact page and its last-updated date, and refers users to regulated advisers instead of giving personal immigration advice.

## Key Contributions

- Built a GOV.UK RAG pipeline covering 15 official guides with section-aware chunking and citation tracking.
- Implemented BGE-small semantic retrieval with Qdrant, topic filtering, and CPU-only embeddings.
- Developed an MCP server with GOV.UK search, postcode lookup, and nearby-service tools, supporting local stdio and Docker HTTP.
- Built an agentic tool-calling loop with step/search limits and code-level guardrails for citations, visa queries, and safe referrals.
- Added provider-agnostic LLM support for OpenAI, Anthropic, Gemini, and Groq with rate limiting and retries.
- Achieved **Recall@5 = 1.00, MRR = 1.00**, with **1.00 tool-selection and citation accuracy** in agent evaluation.
- Containerised the system with Docker Compose, added **31 offline CI tests**, and deployed a public Streamlit demo.
## Project Links

- [GitHub Repository](https://github.com/NafisaIslamRifa/uk-newcomer-assistant)
- [Live Demo](https://uk-newcomer-assistant-uknest-ai.streamlit.app/)

## Technologies Used

- Python
- Model Context Protocol (MCP, FastMCP)
- Qdrant
- fastembed (BAAI/bge-small-en-v1.5)
- Groq (gpt-oss-120b) with OpenAI-compatible, Anthropic and Gemini adapters
- Streamlit
- Docker and Docker Compose
- GitHub Actions (CI)
- GOV.UK Content API, postcodes.io, OpenStreetMap Overpass API
- Retrieval-Augmented Generation (RAG)
- Agentic AI and LLM guardrails
