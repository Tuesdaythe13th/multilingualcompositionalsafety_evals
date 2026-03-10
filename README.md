# ARTIFEX v7 — AI Safety & Dialect Divergence Benchmark Suite

**Principal Investigator**: Tuesday, ARTIFEX Labs

---

## Project Overview

This repository contains the ARTIFEX notebook series, a collection of Google Colab notebooks for advanced AI safety analysis. The project focuses on cutting-edge techniques for identifying and mitigating risks in multilingual and multicultural contexts. It integrates BERTopic clustering, UMAP projections, entropy-based multi-agent safety routing, LLM-as-Judge evaluation, FiftyOne visual annotation, cross-lingual values auditing, and Human-in-the-Loop (HITL) ranking queries.

The research incorporates findings from several 2025-2026 SOTA papers on topics including cross-lingual value alignment, HITL learning, and annotator bias in low-resource languages. It uses multilingual synthetic datasets (e.g., English, Bangla, Hindi, Arabic, Spanish) to test how AI models handle **Consensus Harms** (universally unsafe content) versus **Pluralism Harms** (culturally relative taboos, such as perceptions of beef in India or indoor dogs in Malaysia).

## Notebook Index

| Version | Open in Colab | Description |
|---|---|---|
| **v7.3** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/artifex-v7/blob/main/ARTIFEX_v7.3_Dialect_Divergence.ipynb) | **Dialect Divergence Benchmark**: Analyzes safety blindspots between Castilian Spanish and Mexican Spanish using a 200-pair parallel corpus. | 
| **v7.2** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/artifex-v7/blob/main/ARTIFEX_v7.2_Spanish_Benchmark.ipynb) | **Spanish Benchmark Edition**: Deploys the swarm on a 68-prompt benchmark with Colombian cultural context. | 
| **v7.0** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/artifex-v7/blob/main/ARTIFEX_v7_Compositional_Safety.ipynb) | **Core Multilingual Swarm**: The original multilingual compositional safety system. | 

## Technical Stack & Workflow

#### Key Libraries

| Category | v7.3 Components | Key Enhancement |
|---|---|---|
| **Embedding** | `BAAI/bge-m3` | SOTA 2024 model for nuanced, 1024-dim multilingual embeddings. |
| **Clustering** | BERTopic + HDBSCAN + UMAP | Cross-lingual topic modeling and 3D latent space visualization. |
| **Safety Swarm** | X-Value Consensus/Pluralism Agents | Locale-aware routing with regex-hardened triggers. |
| **Evaluation** | Gemini 2.5 Flash w/ Pydantic | Guaranteed structured JSON outputs via `response_schema`. |
| **Annotation** | FiftyOne | Interactive dashboard for visual dataset curation and error analysis. |
| **EDA** | ydata-profiling | Automated Exploratory Data Analysis reports. |

#### Workflow Highlights

1.  **Data Ingestion**: Supports Colab secrets, Google Drive, local file uploads, or a built-in synthetic multilingual dataset featuring harms like violence, bias, and cultural taboos.
2.  **Analysis Pipeline**: Embeddings → BERTopic clustering → UMAP visualization → Multi-agent swarm inference → LLM-as-Judge evaluation → FiftyOne annotation.
3.  **Outputs**: The notebooks generate cluster themes (e.g., "Cultural Harm"), entropy-based routing decisions (AUTO_APPROVED, ROUTED_TO_HUMAN, AUTO_BLOCKED), and cross-lingual audit pass rates, visualized with Sankey and Radar charts.

*The notebooks feature a brutalist CSS style for all outputs and are for research purposes only.*

---

## Paper Review

A detailed critical review of two 2026 benchmark survey papers — covering Agent-as-a-Judge frameworks, contamination-resistant benchmarks (KAMI), multimodal cultural evaluation (Afri-MCQA, AVMeme Exam), adversarial robustness (CAIA), and agentic SDLC evaluation (DevOps-Gym) — is available in [`PAPER_REVIEW.md`](./PAPER_REVIEW.md). The review includes a direct mapping of findings to ARTIFEX v7.4+ roadmap items.

---

## Future Work & Roadmap (v7.4+)

Based on recent 2026 research, the following production-grade improvements are planned:

| Area | Enhancement | Rationale |
|---|---|---|
| **Entropy Routing** | Dynamic, Calibrated Thresholds | Replace fixed entropy cutoffs with Monte Carlo Dropout or ensemble-based uncertainty to better handle "unknown unknowns." |
| **Red-Teaming** | Automated Adversarial Pipeline | Integrate an automatic red-teaming loop to continuously generate adversarial examples and stress-test the swarm. |
| **HITL Ranking** | Complexity Augmentation | Use LLMs (e.g., WizardCoder) to expand human-authored exemplars with layered constraints, increasing query diversity. |
| **AI Security** | Prompt Injection Detection | Add a dedicated layer to detect and log adversarial manipulation attempts against the swarm and judge agents. |
| **X-Value Audit** | Domain Expansion & Drift Tracking | Expand value domains to include data sovereignty and algorithmic accountability; monitor for Consensus/Pluralism drift over time. |
| **FiftyOne Workflow** | Collaborative Annotation & Quality Gates | Implement visual clustering to find annotation errors and add quality gates (IoU, precision) for annotation batch promotion. |
| **Runtime Dataset Randomization** | KAMI-style Dynamic Augmentation | Randomize entity names, locations, and cultural markers at inference time to eliminate contamination risk in synthetic safety dataset. |
| **Speech-First Evaluation Track** | Audio Modality Benchmarking | Add evaluation track for languages where literacy occurs in non-native script (priority: Swahili, Yoruba, Hausa, Arabic dialects) — text multilingual scores do not transfer to speech (Afri-MCQA finding). |
| **Context Rot Monitoring** | Swarm Routing Consistency vs. Turn Index | Track routing consistency as a function of conversation turn to quantify degradation onset and context budget consumed by FiftyOne/BERTopic outputs. |
| **Adversarial Injection Testing** | CAIA-style Red Team Loop | Test whether X-Value routing agents can be manipulated via SEO-optimized misinformation injected into retrieved cultural context. Log all adversarial attempts. |
| **Escalation Accuracy Metric** | HITL Validation Rate | Post-hoc metric tracking whether ROUTED_TO_HUMAN decisions were validated by human reviewers as genuinely requiring escalation (true positives vs. false escalations). |

## Research References

| Paper | Venue / Source | arXiv / Link |
|---|---|---|
| International AI Safety Report | PR Newswire 2026 | [Link](https://www.prnewswire.com/news-releases/2026-international-ai-safety-report-charts-rapid-changes-and-emerging-risks-302679401.html) |
| Omni-Safety | Feb 2026 | 2602.10161 |
| LPP Entropy Routing | AAMAS 2026 | 2601.07006 |
| Aetheria Governance | Dec 2025 | 2512.02530 |
| Multi3Hate | NAACL 2025 | 2411.03888 |
| Adaptive Boolean Rubrics | Google 2025 | 2503.23339 |
| X-Value Cross-Lingual | Alibaba/ZJU 2026 | 2602.17283 |
| Beyond Labels HITL | Georgia Tech 2026 | 2602.15738 |
| Bangla Annotator Bias | Wichita State 2026 | 2602.16241 |
| Automatic Red-Teaming | Emergent Mind | [Link](https://www.emergentmind.com/topics/automatic-red-team-pipeline) |
| **Afri-MCQA: Multimodal Cultural QA for African Languages** | arXiv Jan 2026 | [2601.05699](https://arxiv.org/abs/2601.05699) |
| **AVMeme Exam: Multimodal Multilingual Multicultural Benchmark** | arXiv Jan 2026 | [2601.17645](https://arxiv.org/abs/2601.17645) |
| **Agent-as-a-Judge Survey** | arXiv Jan 2026 | [2601.05111](https://arxiv.org/abs/2601.05111) |
| **VERA-MH: Ethical AI Validation for Mental Health** | ResearchGate 2026 | [396693427](https://www.researchgate.net/publication/396693427) |
| **CAIA: Adversarial Benchmark for Crypto AI Agents** | arXiv Oct 2025 | [2510.00332](https://arxiv.org/abs/2510.00332) |
| **FinResearchBench: Agent-as-a-Judge for Finance** | ResearchGate 2026 | [397613383](https://www.researchgate.net/publication/397613383) |
| **LOCA-bench: Context Growth Degradation** | arXiv Feb 2026 | [2602.07962](https://arxiv.org/abs/2602.07962) |
| **ToolGym: Open-World Tool-Use Environment** | arXiv Jan 2026 | [2601.06328](https://arxiv.org/abs/2601.06328) |
| **Gaia2: Benchmarking LLM Agents on Dynamic Environments** | arXiv Feb 2026 | [2602.11964](https://arxiv.org/abs/2602.11964) |
| **DevOps-Gym: Benchmarking AI Agents in SDLC** | arXiv Jan 2026 | [2601.20882](https://arxiv.org/abs/2601.20882) |
| **Toolathlon: Tool Decathlon Benchmark** | arXiv Oct 2025 | [2510.25726](https://arxiv.org/abs/2510.25726) |
| **NIST CAISI RFI: Securing AI Agent Systems** | NIST Jan 2026 | [Link](https://www.nist.gov/news-events/news/2026/01/caisi-issues-request-information-about-securing-ai-agent-systems) |
| **AI Language Proficiency Monitor (Jan 2026)** | BibBase / Emergent Mind | [Link](https://www.emergentmind.com/topics/multilingual-benchmarks) |
| **Evaluation & Benchmarking of Generative & Agentic AI** | Preprints.org Dec 2025 | [Link](https://www.preprints.org/manuscript/202512.1421/v1) |
