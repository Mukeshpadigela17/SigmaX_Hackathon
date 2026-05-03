# SigmaX_Hackathon

# BIS Standards Recommendation Engine (RAG Prototype)

This repo contains a proof-of-concept RAG system that recommends BIS Building Material standards based on a product description.

## Setup

```bash
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
pip install -r requirements.txt
```

## Building the Vector Index

Prepare a CSV `data/standards_chunks.csv` with columns: `id`, `title`, `text`, `category`.  
Then run:

```bash
python -m src.data_ingestion data/standards_chunks.csv
```

(You may adapt `data_ingestion.py` to your actual format.)

## Running Inference (for judges)

```bash
python inference.py --input hidden_private_dataset.json --output team_results.json
```

This will produce a JSON with fields: `id`, `retrieved_standards`, `latency_seconds`.
