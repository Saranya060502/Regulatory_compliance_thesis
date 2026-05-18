# Regulatory Compliance Automation via Blended RAG

> **Research paper under review at IEEE COMPSAC 2025**

Automated classification and compliance checking of privacy policies against **GDPR** using a blended Retrieval-Augmented Generation (RAG) architecture that combines dense vector search with structured regulatory knowledge retrieval.

---

## Problem

Organizations publish privacy policies in natural language, but verifying whether they actually comply with regulations like GDPR is a manual, expensive, and error-prone process. A single enterprise may manage hundreds of vendor policies — legal teams can't scale to review them all.

**This research asks:** Can an AI system reliably classify privacy policy clauses against GDPR data practice categories — and flag gaps — without hallucinating regulatory requirements?

---

## Approach: Blended RAG

Standard RAG retrieves context from a flat document store. This project uses a **blended retrieval strategy** that combines:

| Retrieval Layer | What it does |
|---|---|
| Dense semantic search | Finds clauses with similar meaning to GDPR articles |
| Structured knowledge retrieval | Grounds responses in explicit regulatory article mappings |
| LLM reasoning layer | Synthesizes retrieved context to classify and explain compliance |

This hybrid approach reduces hallucination compared to pure generative classification and outperforms keyword-matching approaches on nuanced regulatory language.

---

## Dataset

Uses the **OPP-115 corpus** — a benchmark dataset of 115 real-world website privacy policies, hand-annotated across 10 data practice categories. Extended here with GDPR article mappings to create a compliance-labelled evaluation set.

- `opp115_gdpr_sample_actual_filled.csv` — ground truth human annotations with GDPR mappings
- `opp115_gdpr_with_model_preds.csv` — model predictions vs ground truth for evaluation

---

## Key Files

```
├── week1_data_setup.ipynb          # Data pipeline: OPP-115 ingestion, GDPR mapping, preprocessing
├── opp115_gdpr_sample_actual_filled.csv   # Ground truth labels
└── opp115_gdpr_with_model_preds.csv       # Model output vs ground truth
```

---

## Why This Matters for Enterprise

- **Cisco, AWS, Azure, Google Cloud** all operate under GDPR for EU customers and must vet third-party vendors
- Compliance teams spend thousands of hours manually reviewing privacy policies
- A blended RAG system can flag potential gaps instantly, surfacing only the edge cases for human review
- The same architecture generalizes to other regulatory frameworks: HIPAA, CCPA, SOC 2, FedRAMP

---

## Tech Stack

- Python, Jupyter
- Sentence Transformers (dense retrieval)
- OPP-115 corpus
- GDPR Article taxonomy (custom mapping)
- Pandas for evaluation pipeline

---

## Status

📄 Research paper submitted to and under review at **IEEE COMPSAC** (Computer Software and Applications Conference).

Code reflects the data setup and evaluation pipeline from the paper. Full RAG pipeline code to be released post-review.

---

## Author

**Saranya** — [GitHub](https://github.com/Saranya060502)

*Interested in AI applications for enterprise compliance, NLP, and information retrieval.*
