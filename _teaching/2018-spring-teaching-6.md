---
title: "London NO2 Forecaster: End-to-End MLOps"
collection: teaching
type: "Applied ML / MLOps / Time-Series Forecasting"
permalink: /teaching/2026-london-no2-forecaster-mlops
venue: "Personal MLOps Project"
date: 2026-10-18
location: "London, United Kingdom"
---

Built an end-to-end MLOps system that forecasts next-day nitrogen dioxide (NO₂) at a London roadside monitoring site from live air-quality and weather data. The focus is the lifecycle around the model: versioned data, tracked experiments, a model registry, a containerised API, monitoring, CI/CD and quality-gated retraining. LightGBM reduced test error by about 23% against a persistence baseline.

## Key Contributions

- Built a **data pipeline** over three years of hourly London Air Quality Network (LAQN) NO₂ and weather data, with **pandera validation** (range, duplicate and gap checks) and **DVC** versioning of the ingest and validate stages.
- Engineered **leakage-safe time-series features** (calendar-based lags, rolling means, next-day weather and calendar signals) and wrote a **leakage test** showing that no feature changes when future NO₂ values change.
- Compared a **persistence baseline, Ridge regression and LightGBM** on a time-based split; **LightGBM cut test MAE from 8.16 to 6.31 µg/m³ (22.7%)**, with most of the gain coming from weather and calendar features.
- Tracked every run in **MLflow on DagsHub** (parameters, MAE/RMSE, plots, dataset hash) and promoted the best model through the **model registry** with a `production` alias.
- Served forecasts through a **FastAPI service** (`/forecast`, `/health`, `/metrics`) in a slim, non-root **Docker** image with a health check, loading the registry model at startup with a **baked-in fallback copy**.
- Added **input guardrails and resilience**: the API refuses to forecast through long data gaps, and the weather source falls back from **MET Norway to Open-Meteo to a clearly flagged degraded mode**.
- Monitored the service with **Prometheus and Grafana** locally, and a **Grafana Cloud** dashboard fed by a daily job that checks API status and latency, scores forecasts against actual measurements, and tracks input drift.
- Deployed the image on **Render** from Docker Hub, and automated testing, container smoke tests, image publishing and redeploys with **GitHub Actions**, including **weekly retraining that promotes a new model only if it beats production** on the latest 30 days.
- Added **19 automated tests** covering features, live-data handling, weather providers, ingestion and the API.

## Project Links

- [GitHub Repository](https://github.com/NafisaIslamRifa/london-air-quality)
- [Live API Docs](https://london-air-quality-latest.onrender.com/docs)
- [Docker Hub Image](https://hub.docker.com/r/nafisarifa/london-air-quality)

## Technologies Used

- Python, pandas, pandera
- DVC (data and pipeline versioning)
- scikit-learn (Ridge), LightGBM
- MLflow experiment tracking and model registry (hosted on DagsHub)
- FastAPI, Docker and Docker Compose
- Prometheus, Grafana, Grafana Cloud
- Render (deployment), Docker Hub
- GitHub Actions (CI/CD, scheduled monitoring and retraining)
- LAQN, MET Norway and Open-Meteo data APIs
- pytest
