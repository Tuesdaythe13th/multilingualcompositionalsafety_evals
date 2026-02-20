# ARTIFEX — Spanish Dialect Safety Benchmark Suite

## Notebooks

| Version | Open in Colab | Description |
|---|---|---|
| **v7.3** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/artifex-v7/blob/main/ARTIFEX_v7.3_Dialect_Divergence.ipynb) | **Dialect Divergence** — Spain ES vs Mexico ES, 200-pair benchmark |
| **v7.2** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/artifex-v7/blob/main/ARTIFEX_v7.2_Spanish_Benchmark.ipynb) | Spanish Benchmark Edition — 68 Colombian-context prompts |
| **v7.0** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/artifex-v7/blob/main/ARTIFEX_v7_Compositional_Safety.ipynb) | Original multilingual compositional safety swarm |

## v7.3 Features

- **200-pair aligned dialect corpus** (Spain ES-ES vs Mexico ES-MX)
- **BAAI/bge-m3** SOTA embedding model (1024-dim)
- **Dialect Divergence Visualizations** — category bar chart + divergence scatter plot
- **UMAP 3D Dialect Comparison** — both dialects in the same latent space
- **ARTIFEX Swarm v7.3** — regex word boundaries, dynamic entropy weights
- **Dialect Routing Divergence Sankey** — shows where safety decisions differ by dialect
- All production-grade fixes from code review applied

## Research References

| Paper | Venue | arXiv |
|---|---|---|
| Omni-Safety | Feb 2026 | 2602.10161 |
| LPP Entropy Routing | AAMAS 2026 | 2601.07006 |
| Aetheria Governance | Dec 2025 | 2512.02530 |
| Multi3Hate | NAACL 2025 | 2411.03888 |
| Adaptive Boolean Rubrics | Google 2025 | 2503.23339 |
| X-Value Cross-Lingual | Alibaba/ZJU 2026 | 2602.17283 |
| Beyond Labels HITL | Georgia Tech 2026 | 2602.15738 |
| Bangla Annotator Bias | Wichita State 2026 | 2602.16241 |

© 2026 Artifex Labs
