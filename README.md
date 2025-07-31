## Overview ##
This repo contains a prototype for Retrieval-Augmented Generation (RAG) pipeline designed to generate personalized patient follow-up messages based on medical charts. Built as part of my work at Sunnybrook Research Institute, it leverages large language models (LLMs) to create empathetic, resource-oriented messages for patients discharged from critical care.

The pipeline processes patient charts by chunking them into sentence-level segments, expands user queries for better retrieval, uses BM25 for intial ranking, reranks with embeddings and generates responses using Qwen-30B. This approach addresses semantic challenges in medical text, ensurnig relevant and context-aware outputs.

**Note:** This a sanitized prototype with no real patient data. All examples use synthetic or placeholder data generated via GPT-4. It's intended for demonstration and educational purposes only.

## Features ##
- **Chunking and Indexing:** Breaks down patient charts into sentence-level chunks for efficient retrieval.
- **Query Expansion:** Automatically expands user queries i.e. "What are next steps for the patient?" into sub-propositions to handle semantic dissimilarity in medica contexts.
- **Hybrid Retrieval:** Combines BM25 for fast keyword-based top-100 matches with Qwen embeddings for reranking to top-10.
- **Generation:** Uses Qwen-30B to synthesize for generating messages from retrieved contexts.

## Requirements ##
- Python 3.10+
- Libraries: rank_bm25, transformers, openai, numpy, pandas
- Models: Qwen-30B and Qwen embeddings model