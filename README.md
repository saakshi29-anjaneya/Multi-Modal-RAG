## Multimodal RAG for Text and Image Retrieval

This project implements a **Multimodal Retrieval-Augmented Generation (RAG)** system for the automotive domain. It combines text and image retrieval with a generative language model to produce context-aware, grounded responses to user queries.

The system follows the architecture and principles described in the paper *Multi-modal RAG for Text and Image Retrieval*, adapting them to large-scale automotive data.

---

## Overview

The pipeline integrates multiple representation and retrieval components:

* **CLIP** for joint image–text embedding alignment
* **Sentence Transformers (MiniLM)** for textual semantic embeddings
* **FAISS** for efficient similarity search over high-dimensional vectors
* **LLM-based generation** to synthesize coherent, retrieval-grounded answers

User queries retrieve semantically relevant vehicle images and specifications, which are then used as context for response generation. The system is designed to remain brand-agnostic while maintaining factual grounding.

---

## Pipeline Stages

### 1. Data Acquisition and Consolidation

Automotive metadata from multiple manufacturers is collected, standardized, and merged into a unified schema.

### 2. Semantic Embedding and Indexing

* Text embeddings generated using MiniLM
* Image embeddings generated using CLIP
* All embeddings indexed using FAISS for fast similarity search

### 3. Query Processing and Retrieval

User queries are embedded and matched against the indexed vectors to retrieve the top-K most relevant textual and visual items.

### 4. Generative Answer Synthesis

Retrieved context is passed to a language model, which generates natural-language responses grounded in the retrieved specifications and images.

---

## Dataset

* Automotive data from **Hyundai, Tata, Mahindra, and Maruti Suzuki**
* Approximately **150 car variants**
* Around **1,500 images** with structured JSON metadata
* Stored in compressed form due to repository size constraints

---

## Results (Summary)

* **Top-1 Accuracy:** 82%
* **Top-3 Accuracy:** 90%
* **Top-5 Accuracy:** 94%
* **Average Retrieval Time:** ~0.32 seconds per query

These results highlight the performance gains achieved through multimodal fusion compared to unimodal retrieval approaches.

---

## Notes

* Intended for research, learning, and experimentation
* Large datasets are managed externally due to GitHub size limits
* Ensure all required models and dependencies are available before running the pipeline

---
