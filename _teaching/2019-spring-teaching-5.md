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

- Built an ingestion pipeline on the GOV.UK Content API covering 15 official guides, with section-aware chunking so every citation points to a specific page heading and last-updated date.
- Implemented semantic retrieval with BGE-small embeddings (fastembed / ONNX, CPU-only) and a Qdrant vector database with topic filtering. Qdrant runs as a server, in the cloud or embedded in the app.
- Exposed the system's capabilities as a Model Context Protocol (MCP) tool server with three tools: GOV.UK guidance search, postcode lookup (postcodes.io), and nearby-service search (OpenStreetMap). The same server runs over stdio locally and over HTTP in Docker.
- Designed an agent loop in which the LLM chooses and combines tools, with limits enforced in code: a maximum number of steps and a cap on searches per question.
- Added code-level guardrails beyond prompting: every cited URL is checked against tool results, personal visa questions are detected and answered without a yes/no verdict, and an OISC / Citizens Advice referral is added when needed.
- Built a provider-agnostic LLM layer (OpenAI-compatible, Anthropic and Gemini adapters) with client-side rate limiting and retry handling. When one provider's free tier became too restrictive, the live demo moved to Groq (gpt-oss-120b) by changing configuration only, with no code changes.
- Evaluated the system end to end. Retrieval reached Recall@5 = 1.00 and MRR = 1.00 on direct questions. An agent evaluation measures tool selection (1.00), citation accuracy (1.00), safe deferral and invented-link rate, and its failures led to fixes in code.
- Packaged the system with Docker Compose (Qdrant, index-building job, MCP server and UI), set up GitHub Actions CI with 31 offline unit tests, and deployed a public demo on Streamlit Community Cloud.

## Project Links

- [GitHub Repository](https://github.com/NafisaIslamRifa/uk-newcomer-assistant)
- [Live Demo](https://YOUR-APP.streamlit.app)

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
