# ARTIFEX v7.1 — Compositional Safety Routing

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/artifex-v7/blob/main/ARTIFEX_v7_Compositional_Safety.ipynb)

> **State-of-the-art multimodal content safety analysis** using 2025-2026 SOTA research. Multilingual, culturally-aware, with LLM-as-Judge evaluation, FiftyOne visual annotation, and information-efficient HITL ranking.

## What's New in v7.1

| Feature | Description | Paper |
|---|---|---|
| **LLM-as-Judge** | Adaptive Precise Boolean Rubrics replace Likert scales | arXiv:2503.23339 |
| **FiftyOne Annotation** | Voxel51 visual curation for flagged multimodal content | docs.voxel51.com |
| **X-Value Audit** | Cross-lingual Consensus/Pluralism values assessment (18 langs) | arXiv:2602.17283 |
| **HITL Ranking** | Information-efficient ranking & exemplar selection queries | arXiv:2602.15738 |
| **Multilingual Embedding** | paraphrase-multilingual-MiniLM-L12-v2 (50+ languages) | arXiv:1908.10084 |
| **Multicultural Swarm** | Bangla/Hindi/Arabic harm detection in safety agents | arXiv:2602.16241 |

## Full Research Stack

| Paper | arXiv | Cell |
|---|---|---|
| BERTopic | 2203.05794 | 05 |
| UMAP | 1802.03426 | 05.1 |
| Omni-Safety (Cross-Modal) | 2602.10161 | 06 |
| LPP Entropy Routing | 2601.07006 | 06 |
| Aetheria Governance | 2512.02530 | 06 |
| Multi3Hate | 2411.03888 | 06 |
| Adaptive Boolean Rubrics | 2503.23339 | 07 |
| FiftyOne Visual Annotation | — | 08 |
| X-Value Cross-Lingual | 2602.17283 | 10 |
| Beyond Labels HITL | 2602.15738 | 11 |
| Bangla Annotator Bias | 2602.16241 | 04, 10 |

## Notebook Structure (29 cells)

```
00 README + Open in Colab
01 ENV Setup (multilingual SOTA stack)
02 Data Ingestion (multilingual synthetic fallback)
03 Automated EDA (ydata-profiling)
04 Multilingual Embedding (50+ languages)
05 BERTopic Clustering
05.1 UMAP 3D Multilingual Projection
06 ARTIFEX Swarm v7.1 (Consensus/Pluralism layer)
07 LLM-as-Judge (Boolean Rubrics) ← NEW
08 FiftyOne Visual Annotation ← NEW
09 LLM Cluster Synthesis
10 X-Value Cross-Lingual Audit ← NEW
11 HITL Ranking & Exemplar Selection ← NEW
12 Multilingual Sankey Flow
13 Environment Audit
```

## Contact

- **Linktree**: [linktr.ee/artifexlabs](https://linktr.ee/artifexlabs)
- **HuggingFace**: [huggingface.co/222tuesday](https://huggingface.co/222tuesday)

© 2026 Artifex Labs. Research & demonstration purposes only.
