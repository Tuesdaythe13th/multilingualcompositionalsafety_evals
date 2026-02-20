# ARTIFEX v7.0: Compositional Safety & Ethical AI Feedback Analysis

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/artifex-v7/blob/main/ARTIFEX_v7_Compositional_Safety.ipynb)

> **Principal Investigator**: Tuesday @ ARTIFEX Labs  
> **Version**: 7.0.0 — Updated with 2025-2026 SOTA Research  
> **Contact**: tuesday@artifexlabs | [linktr.ee/artifexlabs](https://linktr.ee/artifexlabs)

---

## Overview

**ARTIFEX v7.0** is a state-of-the-art Google Colab notebook demonstrating **Compositional Safety Routing** — the detection of emergent harm that arises from the combination of individually safe content components. This is a major upgrade from v6.1, incorporating the latest 2025-2026 research in multimodal safety, entropy-based routing, and semantic clustering.

## Key Upgrades from v6.1

| Feature | v6.1 | v7.0 (2026 SOTA) |
|---|---|---|
| Clustering | K-Means | **BERTopic** (UMAP + HDBSCAN + c-TF-IDF) |
| Visualization | PCA 3D | **UMAP 3D** (topology-preserving) |
| Safety Routing | Rule-based entropy | **LPP-based entropy** (AAMAS 2026) |
| Cross-modal Safety | Basic compositional rules | **OmniSteer-inspired** modality decoupling |
| Cultural Context | 3 locales | **5 locales** + Multi3Hate findings |
| Governance | Simple rubrics | **Aetheria-inspired** interpretable audit trails |

## Notebook Structure

| Cell | Title | Description |
|---|---|---|
| 00 | README | Project overview, citations, legal disclaimer |
| 01 | ENV_INITIALIZATION | SOTA dependency installation (BERTopic, UMAP, etc.) |
| 02 | DATA_INGESTION | Flexible data loading (Secrets/Drive/Upload/Synthetic) |
| 03 | AUTOMATED_EDA | ydata-profiling comprehensive report |
| 04 | TRANSFORMER_EMBEDDING | all-MiniLM-L6-v2 sentence embeddings |
| 05 | BERTopic_CLUSTERING | SOTA topic modeling with auto-detected clusters |
| 05.1 | UMAP_PROJECTION | Interactive 3D latent space visualization |
| 06 | COMPOSITIONAL_SAFETY | 6-agent swarm with entropy-based routing |
| 07 | LLM_SYNTHESIS | Cluster theme generation (Gemini 2.0 Flash ready) |
| 08 | SANKEY_DYNAMICS | Cluster-to-Rating semantic flow analysis |
| 09 | ENVIRONMENT_AUDIT | Watermark tracking for reproducibility |

## Key Research References (2025-2026)

1. **Omni-Safety under Cross-Modality Conflict** (Feb 2026) — arXiv:2602.10161
2. **LLM Performance Predictors: Learning When to Escalate** (AAMAS 2026) — arXiv:2601.07006
3. **Aetheria: Multi-Agent Debate Content Safety** (Dec 2025) — arXiv:2512.02530
4. **Multi3Hate: Multicultural Hate Speech Detection** (NAACL 2025) — arXiv:2411.03888
5. **Large-Scale Knowledge Profiling with UMAP+HDBSCAN** (Jan 2026) — arXiv:2601.15170

## How to Cite

```
Artifex Labs (2026). ARTIFEX v7.0: Compositional Safety & Ethical AI Feedback Analysis.
Version 7.0. [Google Colab Notebook]. https://github.com/Tuesdaythe13th/artifex-v7
```

## Legal Disclaimer

© 2026 Artifex Labs. This notebook is provided "as-is" for research purposes only. Redistribution without written permission is prohibited.
