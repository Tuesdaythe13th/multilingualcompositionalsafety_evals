```
 █████╗ ██████╗ ████████╗██╗███████╗███████╗██╗  ██╗    ██╗      █████╗ ██████╗ ███████╗
██╔══██╗██╔══██╗╚══██╔══╝██║██╔════╝██╔════╝╚██╗██╔╝    ██║     ██╔══██╗██╔══██╗██╔════╝
███████║██████╔╝   ██║   ██║█████╗  █████╗   ╚███╔╝     ██║     ███████║██████╔╝███████╗
██╔══██║██╔══██╗   ██║   ██║██╔══╝  ██╔══╝   ██╔██╗     ██║     ██╔══██║██╔══██╗╚════██║
██║  ██║██║  ██║   ██║   ██║██║     ███████╗██╔╝ ██╗    ███████╗██║  ██║██████╔╝███████║
╚═╝  ╚═╝╚═╝  ╚═╝   ╚═╝   ╚═╝╚═╝     ╚══════╝╚═╝  ╚═╝    ╚══════╝╚═╝  ╚═╝╚═════╝ ╚══════╝

        ██╗   ██╗███████╗    ███████╗ █████╗ ███████╗███████╗████████╗██╗   ██╗
        ██║   ██║╚════██║    ██╔════╝██╔══██╗██╔════╝██╔════╝╚══██╔══╝╚██╗ ██╔╝
        ██║   ██║    ██╔╝    ███████╗███████║█████╗  █████╗     ██║    ╚████╔╝
        ╚██╗ ██╔╝   ██╔╝     ╚════██║██╔══██║██╔══╝  ██╔══╝     ██║     ╚██╔╝
         ╚████╔╝    ██║      ███████║██║  ██║██║     ███████╗   ██║      ██║
          ╚═══╝     ╚═╝      ╚══════╝╚═╝  ╚═╝╚═╝     ╚══════╝   ╚═╝      ╚═╝

  ╔══════════════════════════════════════════════════════════════════════════════╗
  ║  COMPOSITIONAL SAFETY  ·  CROSS-LINGUAL VALUES  ·  ADAPTIVE BOOL RUBRICS   ║
  ║  BBOM SUPPLY-CHAIN AUDIT  ·  LLM-AS-JUDGE  ·  FIFTYONE MODEL EVALUATION    ║
  ║  IRT-CALIBRATED BENCHMARKS  ·  NIST AI 800-3  ·  ISO/IEC 42119             ║
  ╚══════════════════════════════════════════════════════════════════════════════╝
```

```
 ████████╗██╗   ██╗███████╗███████╗██████╗  █████╗ ██╗   ██╗
 ╚══██╔══╝██║   ██║██╔════╝██╔════╝██╔══██╗██╔══██╗╚██╗ ██╔╝
    ██║   ██║   ██║█████╗  ███████╗██║  ██║███████║ ╚████╔╝
    ██║   ██║   ██║██╔══╝  ╚════██║██║  ██║██╔══██║  ╚██╔╝
    ██║   ╚██████╔╝███████╗███████║██████╔╝██║  ██║   ██║
    ╚═╝    ╚═════╝ ╚══════╝╚══════╝╚═════╝ ╚═╝  ╚═╝   ╚═╝

  ╔══════════════════════════════════════════════════════╗
  ║  Principal Engineer  ·  ARTIFEX Labs                 ║
  ║  tuesday@artifex.fun                                 ║
  ║  linktr.ee/artifexlabs                               ║
  ║  huggingface.co/222tuesday                           ║
  ║  contact: zcal.co/tuesday                            ║
  ╚══════════════════════════════════════════════════════╝
```

**Principal Investigator**: Tuesday, ARTIFEX Labs  
**Framework**: 3D Measurement Science in the Era of Frontier Intelligence (2026)  
**Standards**: NIST AI 800-3 · ISO/IEC 42119-2/3 · MLCommons AILuminate  
**Branch**: `main`

---

## Overview

ARTIFEX LABS v7 is a multilingual compositional safety evaluation suite that benchmarks AI content-safety pipelines across languages, dialects, and cultural contexts. The suite implements:

- **X-Value Consensus/Pluralism framework** for cross-lingual value alignment auditing
- **Adaptive Boolean Rubrics** — machine-checkable, auditable gates at every pipeline decision point
- **BBOM (Benchmark Bill of Materials)** supply-chain auditing for benchmark validity
- **LLM-as-Judge** with bias-corrected estimators and Pydantic structured outputs
- **Human-in-the-Loop (HITL)** triplet active learning queries
- **FiftyOne** visual dataset curation for multimodal annotation

Each notebook is a self-contained Google Colab experiment — click any badge below to run immediately.

---

## Quick Start

### Prerequisites

- A Google account (for Google Colab)
- *(Optional)* API keys for LLM cells — add to Colab Secrets as `OPENAI_API_KEY` or `ANTHROPIC_API_KEY`

### Run a Notebook

1. Click any **"Open in Colab"** badge below
2. In Colab: **Runtime → Run all** (or run cells individually)
3. When prompted, upload data files or enter API keys via the Colab Secrets panel

### Run Locally

```bash
git clone https://github.com/Tuesdaythe13th/multilingualcompositionalsafety_evals.git
cd multilingualcompositionalsafety_evals
pip install bertopic hdbscan umap-learn sentence-transformers pandas pandera plotly scikit-learn
jupyter notebook
```

---

## Notebook Index

> All notebooks include a § 2026 Measurement Science cell mapping methodology to NIST AI 800-3 GLMMs, IRT 3PL construct validity, and the five facets of validity.

| Notebook | Open in Colab | Description | Validity Facet |
|---|---|---|---|
| **safety_routing** ★ | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/main/safety_routing_colab.ipynb) | **Ethical AI Feedback Loop Analysis** — Full Artifex Labs v3.1: uv install, Colab Secrets, ydata-profiling EDA, sentence-transformers embeddings, K-Means clustering, LLM summarization (OpenAI/Anthropic/extractive), Brutalist HTML explainers, %watermark audit. | Consequential validity |
| **v7.1 Core Swarm** ★ | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/main/ARTIFEX_v7_Compositional_Safety.ipynb) | **Core Multilingual Swarm** — Adaptive boolean rubrics, jury routing, dual-encoder embeddings, HDBSCAN soft memberships, calibrated LLM-as-judge, triplet HITL, FiftyOne model evaluation. | Construct validity |
| **v7.2 Spanish** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/main/ARTIFEX_v7.2_Spanish_Benchmark.ipynb) | **Spanish Benchmark Edition** — 68-prompt Colombian-context benchmark, X-Value Radar charts, DIF detection, bias-corrected LLM-as-Judge. | Content validity |
| **v7.3 Dialect** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/main/ARTIFEX_v7.3_Dialect_Divergence.ipynb) | **Dialect Divergence Benchmark** — Castilian vs. Mexican Spanish, 200-pair parallel corpus, IRT-based DIF analysis, common-person linking. | External validity |
| **v7.4 Feedback Loop** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/main/ARTIFEX_v7.4_Ethical_Feedback_Loop.ipynb) | **Ethical Feedback Loop** — Agentic benchmarking, time-horizon metric, propensity vs. capability distinction. | Consequential validity |
| **v7.5 English** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/main/ARTIFEX_v7.5_English_Cultural_Alignment.ipynb) | **English Cultural Alignment** — US/UK/AU English dialects, spelling/idiom/politeness variation, per-sample IRT θ̂ metrics. | Criterion validity |
| **v8 Agentic** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/main/ARTIFEX_v8_Agentic_Alignment_Engine.ipynb) | **Agentic Alignment Engine** — LangGraph routing, VLM auditing, automated adversarial red-teaming, multi-agent safety alignment. | Construct validity |
| **Evaluator Guide** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/main/ARTIFEX_Evaluator_Design_Guide.ipynb) | **Evaluator Design Guide** — Pedagogical walkthrough of all three evaluator architectures, mechanistic interpretability, rubric engineering, 2026 SOTA model selection. | — |
| **Spanish AILuminate** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/main/spanish_ailuminate_hf_colab.ipynb) | **Spanish AILuminate Jailbreaking** — 500 prompts × 4 categories, Qwen3-235B MUT, 3-judge majority voting (JSR/CCR metrics), BLOCK/WARNING/PASS gates. | Content validity |
| **Fairness Dashboard** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/main/fairness_failure_dashboard.ipynb) | **Cohort Fairness & Failure Clusters** — Loads `results/*_metrics.json`, per-language micro_f1 gap analysis, structured failure cluster manifest. | External validity |

---

## 2026 Research Landscape

> Selected papers informing ARTIFEX methodology — all published 2025–2026.

| Paper | Venue | Link | ARTIFEX Application |
|---|---|---|---|
| Benchmark Bill of Materials (BBOM) | NIST 2026 | Supply-chain framing | All 11 pipeline rubric gates |
| Adaptive Precise Boolean Rubrics | Google 2025 | [arXiv:2503.23339](https://arxiv.org/abs/2503.23339) | BooleanRubricResult dataclass |
| X-Value Cross-Lingual Values | Alibaba/ZJU 2026 | [arXiv:2602.17283](https://arxiv.org/abs/2602.17283) | Consensus/Pluralism audit layer |
| Beyond Labels HITL | Georgia Tech 2026 | [arXiv:2602.15738](https://arxiv.org/abs/2602.15738) | Triplet active learning queries |
| Jailbreak Distillation | Johns Hopkins/MSFT 2025 | [arXiv:2505.22037](https://arxiv.org/abs/2505.22037) | Renewable safety benchmarking |
| Scales of Justitia: Safety Eval Survey | 2025 | [arXiv:2506.11094](https://arxiv.org/abs/2506.11094) | 4D taxonomy (Why/What/Where/How) |
| Beyond Words: Multilingual Red Teaming | ACL 2025 | [ACL Anthology](https://aclanthology.org/2025.llmsec-1.15.pdf) | Multilingual attack surface analysis |
| LPP Entropy Routing | AAMAS 2026 | [arXiv:2601.07006](https://arxiv.org/abs/2601.07006) | Jury routing architecture |
| Omni-Safety | Feb 2026 | [arXiv:2602.10161](https://arxiv.org/abs/2602.10161) | Comprehensive safety scope |
| Multi3Hate | NAACL 2025 | [arXiv:2411.03888](https://arxiv.org/abs/2411.03888) | Multilingual hate speech baselines |
| Afri-MCQA | arXiv Jan 2026 | [arXiv:2601.05699](https://arxiv.org/abs/2601.05699) | African language multimodal gaps |
| SAGE Safety Framework | EMNLP 2025 | [arXiv:2504.19674](https://arxiv.org/abs/2504.19674) | Generic safety eval pipeline |
| International AI Safety Report 2026 | 2026 | [Link](https://internationalaisafetyreport.org) | Frontier safety standards |
| CAIA Adversarial Benchmark | arXiv Oct 2025 | [arXiv:2510.00332](https://arxiv.org/abs/2510.00332) | Adversarial robustness gates |
| Gaia2 Dynamic Environments | arXiv Feb 2026 | [arXiv:2602.11964](https://arxiv.org/abs/2602.11964) | Context rot detection |
| RubricBench | arXiv 2026 | [arXiv:2603.01562](https://arxiv.org/abs/2603.01562) | Human vs. model rubric quality |
| Bangla Annotator Bias | Wichita State 2026 | [arXiv:2602.16241](https://arxiv.org/abs/2602.16241) | Annotator bias correction |
| Aetheria Governance | Dec 2025 | [arXiv:2512.02530](https://arxiv.org/abs/2512.02530) | AI governance alignment |

---

## 2026 Measurement Science Framework

> *"The structural maturation of artificial intelligence as a field of scientific inquiry has necessitated a fundamental transition from simplistic task-based benchmarking to the comprehensive application of measurement science."*  
> — NIST AI 800-3, 2026

### IRT 3PL Model — Item-Level Diagnostics

```
P_i(θ) = c_i + (1 - c_i) / (1 + exp(-a_i * (θ - b_i)))

where:
  a_i = discrimination   (BBOM Layer 3 gate: a_i > 0 required)
  b_i = difficulty       (stored as sample.difficulty in FiftyOne)
  c_i = pseudo-guessing  (default 0.1 for 3-class safety)
```

Items with **negative discrimination** (a_i < 0) indicate annotation errors — a hard BBOM Layer 9 failure gate.

### NIST AI 800-3 GLMM Variance Decomposition

```
Total Variance
  = Between-Item Variance  (difficulty b_i)
  + Within-Item Variance   (jury disagreement rate)
  + Cross-Lingual Variance (DIF — dialect divergence score)
  + Residual               (annotation noise)
```

### Five Facets of Validity — Notebook Mapping

| Validity Facet | Notebook | Primary Instrument |
|---|---|---|
| **Content** | v7.2 (Spanish Benchmark) | `cultural_taxonomy.yaml` × BCP-47 coverage |
| **Construct** | v7.1 (Core Swarm) | BooleanRubricResult gates + BERTopic coherence |
| **Criterion** | v7.5 (English Cultural) | `evaluate_classifications()` + IRT θ̂ |
| **External** | v7.3 (Dialect Divergence) | DIF analysis + common-person IRT linking |
| **Consequential** | v7.4 + safety_routing | Time-horizon metric + feedback loop audit |

### Standards Alignment

| Standard | Version | ARTIFEX Implementation |
|---|---|---|
| NIST AI 800-3 | 2026 | GLMM variance decomposition, benchmark vs. generalized accuracy |
| ISO/IEC 42119-2 | Oct 2025 | Testing techniques across AI lifecycle |
| ISO/IEC 42119-3 | Oct 2025 | Verification & validation approaches |
| MLCommons AILuminate | 2026 | Structured risk assurance, BBOM supply-chain audit |
| BBOM (Benchmark Bill of Materials) | Layer 1–10 | All 11 pipeline rubric gates |

---

## Pipeline Architecture

### Adaptive Boolean Rubric Infrastructure

```python
@dataclass
class BooleanRubricResult:
    name: str           # machine-readable gate name
    passed: bool        # routing decision
    confidence: float
    escalate: bool
    severity: str       # HIGH / MEDIUM / LOW / INFO
    reason: str
    evidence: dict      # raw decision values

RUBRIC_LOG = []         # appended for every rubric; audited in Cell 13
```

### 11 Pipeline Rubric Gates

```
  ┌──────────────────────────────────────────────────────────────────────┐
  │                   PIPELINE RUBRIC LAYERS                             │
  ├──────────────┬───────────────────────────────────┬───────────────────┤
  │  LAYER       │  BOOLEAN GATE                     │  FAIL ROUTES TO   │
  ├──────────────┼───────────────────────────────────┼───────────────────┤
  │  Dataset     │  dataset_size_sufficient           │  LOW_STAT_POWER   │
  │  Dataset     │  coverage_metadata_present        │  BBOM_L9_FAILED   │
  │  Dataset     │  dialect_validated                │  MEASUREMENT_RISK │
  │  Embedding   │  embedding_ensemble_ready         │  single-mode only │
  │  Clustering  │  soft_membership_available        │  hard-assign only │
  │  Clustering  │  cluster_stability_sufficient     │  UNSTABLE_TOPICS  │
  │  Judge       │  human_calibration_present        │  no calib. claims │
  │  Judge       │  judge_bias_correctable           │  human-only report│
  │  Routing     │  jury_disagreement_high           │  HITL             │
  │  Routing     │  ontological_veto_triggered       │  benchmark failure│
  │  HITL        │  active_learning_triplets_avail.  │  no triplet query │
  └──────────────┴───────────────────────────────────┴───────────────────┘
```

### Jury Routing vs. Entropy Threshold

```python
# Old routing (brittle):
if entropy > 0.9: route = "ROUTED_TO_HUMAN"

# New routing (auditable):
jury  = jury_vote(verdicts)
route, jury_rubric, veto_rubric = route_item(jury, soft_gap, ontological_veto)
# → ONTOLOGICAL_VETO | ROUTED_TO_HUMAN | UNSAFE | SAFE
```

---

## Technical Stack

| Category | Components | Notes |
|---|---|---|
| **Embedding** | RoBERTuito + multilingual-E5-Large (ensemble) | Fallback: paraphrase-multilingual-MiniLM-L12-v2 |
| **Clustering** | BERTopic + HDBSCAN (soft memberships) + UMAP | `prediction_data=True`, leaf/eom auto-select |
| **Schema** | Pandera `DataFrameSchema` | Validates coverage metadata at ingestion |
| **Rubrics** | `BooleanRubricResult` dataclass | 11 gates across all pipeline layers |
| **Routing** | `jury_vote()` + `route_item()` | Replaces entropy threshold |
| **Judge** | Bias-corrected θ̂ estimator | Zheng et al. arXiv:2503.23339 |
| **HITL** | Triplet active learning | Beyond Labels arXiv:2602.15738 |
| **Annotation** | FiftyOne (Voxel51) | Visual dataset curation dashboard |
| **EDA** | ydata-profiling | Automated profiling reports |
| **Package Mgr** | `uv` (Astral) | 10-100x faster than pip in Colab 2026 |
| **Audit** | RUBRIC_LOG + BBOM claim gates + %watermark | Full run dumped in final cell |

---

## Annotation Guideline

The **Cultural Appropriateness Annotation Guideline v1.0** provides the master rubric and decision framework for evaluating AI model responses across multilingual and multicultural contexts:

- Two-step rating protocol (appropriateness label + harm severity scale 1–5)
- Ten-dimension cultural taxonomy with decision trees
- 50-item master Boolean rubric (5 items per dimension)
- IRR targets: ICC ≥ 0.80, Cohen's κ ≥ 0.75
- Ethical labor provisions for annotators

Full guideline: [`ANNOTATION_GUIDELINE.md`](./ANNOTATION_GUIDELINE.md)

---

## Future Work & Roadmap

| Area | Enhancement | Rationale |
|---|---|---|
| **Dataset Scale** | Integrate public HuggingFace safety datasets (≥500 items) | Unblocks `dataset_size_sufficient` rubric |
| **Calibration** | Collect ≥30-item human calibration set | Unblocks `human_calibration_present` |
| **Topic Quality** | Add gensim C_V coherence + topic diversity rubrics | Semantic gates replace silhouette proxy |
| **Entropy Routing** | Monte Carlo Dropout uncertainty | Complement jury voting with epistemic uncertainty |
| **Red-Teaming** | Automated adversarial pipeline | KAMI contamination resistance testing |
| **X-Value Audit** | Domain expansion + drift tracking | Data sovereignty, algorithmic accountability |
| **Speech Track** | Audio modality benchmarking | Swahili, Yoruba, Hausa, Arabic (Afri-MCQA) |
| **Context Rot** | Routing consistency vs. turn index | Quantify degradation onset in long contexts |

---

## License

This project is provided for **research and educational purposes only**. Not intended for production deployment without independent verification. See individual notebook headers for specific terms.

---

```
  ╔═══════════════════════════════════════════════════════════════════╗
  ║  ARTIFEX LABS  ·  FOR RESEARCH PURPOSES ONLY                     ║
  ║  Tuesday  ·  2026  ·  tuesday@artifex.fun  ·  zcal.co/tuesday    ║
  ║  linktr.ee/artifexlabs  ·  huggingface.co/222tuesday             ║
  ║  github.com/Tuesdaythe13th                                       ║
  ╚═══════════════════════════════════════════════════════════════════╝
```
