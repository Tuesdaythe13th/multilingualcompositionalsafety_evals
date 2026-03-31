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
- *(Optional)* A Gemini API key for LLM-as-Judge cells — add to Colab Secrets as `GEMINI_API_KEY`

### Run a Notebook

1. Click any **"Open in Colab"** badge below
2. In Colab: **Runtime → Run all** (or run cells individually)
3. When prompted, upload required data files (each notebook includes inline fallback data for demo purposes)

### Run Locally

```bash
git clone https://github.com/Tuesdaythe13th/multilingualcompositionalsafety_evals.git
cd multilingualcompositionalsafety_evals
pip install bertopic hdbscan umap-learn sentence-transformers pandas pandera plotly scikit-learn
jupyter notebook
```

---

## What's New — Adaptive Boolean Rubrics

> Every critical pipeline decision now returns a structured
> `BooleanRubricResult(passed, confidence, evidence, escalate, severity, reason)`
> instead of a raw score or free-text summary. Routing is machine-checkable,
> auditable, and BBOM-aligned throughout.

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

---

## Notebook Index

> Each notebook now includes a **§ 2026 Measurement Science Framework** cell that maps its methodology to NIST AI 800-3 GLMMs, IRT 3PL construct validity, and the five facets of validity.

| Version | Open in Colab | Description | Measurement Science Contribution |
|---|---|---|---|
| **safety_routing** 🆕 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/main/safety_routing_colab.ipynb) | **Ethical AI Feedback Loop** — K-Means clustering + LLM summarization of user feedback; Bokeh dashboard; extractive fallback; ydata-profiling EDA. | **Consequential validity** — cluster coherence as proxy for feedback signal quality |
| **fairness_dashboard** 🆕 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/main/fairness_failure_dashboard.ipynb) | **Cohort Fairness & Failure Clusters** — Loads `results/*_metrics.json`, visualizes per-language/locale micro_f1 gaps, exports structured failure cluster manifest. | **External validity** — cross-slice language gap analysis |
| **spanish_ailuminate** 🆕 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/main/spanish_ailuminate_hf_colab.ipynb) | **Spanish AILuminate Jailbreaking** — 500 prompts × 4 categories; Qwen3-235B MUT; 3-judge majority voting; JSR/CCR metrics; BLOCK/WARNING/PASS gates; JSON evidence bundle. | **Content validity** — multi-locale jailbreak coverage; BBOM supply-chain audit |
| **v7.5** 🆕 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/claude/add-model-evaluation-DxOpU/ARTIFEX_v7.5_FiftyOne_Model_Evaluation.ipynb) | **FiftyOne Model Evaluation** — Full `evaluate_classifications()` pipeline: per-sample metrics, confusion matrices, PR curves, IRT item analysis, scenario analysis, BBOM compliance gate. | **Criterion validity** — per-sample accuracy as IRT observed score; NIST GLMM variance decomposition |
| **v7.1** ★ | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/claude/add-model-evaluation-DxOpU/ARTIFEX_v7_Compositional_Safety.ipynb) | **Core Multilingual Swarm** — Adaptive boolean rubrics, jury routing, dual-encoder embeddings, HDBSCAN soft memberships, calibrated LLM-as-judge, triplet HITL, **FiftyOne model evaluation**. | **Construct validity** — BooleanRubricResult gates + BBOM Layer 9 |
| **v7.4** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/master/ARTIFEX_v7.4_Ethical_Feedback_Loop.ipynb) | **Ethical Feedback Loop** — Agentic benchmarking, time-horizon metric, propensity vs. capability distinction. | **Consequential validity** — alignment propensity measurement |
| **v7.3** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/master/ARTIFEX_v7.3_Dialect_Divergence.ipynb) | **Dialect Divergence Benchmark** — Castilian vs. Mexican Spanish, 200-pair parallel corpus, DIF analysis. | **External validity** — common-person IRT linking across dialects |
| **v7.2** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/master/ARTIFEX_v7.2_Spanish_Benchmark.ipynb) | **Spanish Benchmark Edition** — 68-prompt Colombian-context benchmark, X-Value Radar charts, DIF detection. | **Content validity** — cultural taxonomy + construct coverage mapping |

---

## 2026 Measurement Science Framework

> *"The structural maturation of artificial intelligence as a field of scientific inquiry has necessitated a fundamental transition from simplistic task-based benchmarking to the comprehensive application of measurement science."*
> — NIST AI 800-3, 2026

ARTIFEX v7.x implements the **2026 state-of-the-art** in AI evaluation measurement science. Every notebook is aligned to the following theoretical foundations:

### IRT 3PL Model — Item-Level Diagnostics

The probability of a correct safety verdict on item *i* by a model with latent ability θ:

```
P_i(θ) = c_i + (1 - c_i) / (1 + exp(-a_i * (θ - b_i)))

where:
  a_i = discrimination   (BBOM Layer 3 gate: a_i > 0 required)
  b_i = difficulty       (stored as sample.difficulty field in FiftyOne)
  c_i = pseudo-guessing  (default 0.1 for 3-class safety)
```

Items with **negative discrimination** (a_i < 0) indicate annotation errors — a hard BBOM Layer 9 failure gate.

### NIST AI 800-3 GLMM Variance Decomposition

```
Total Variance
  = Between-Item Variance  (difficulty b_i — item characteristic curves)
  + Within-Item Variance   (model inconsistency — jury disagreement rate)
  + Cross-Lingual Variance (DIF — dialect divergence score)
  + Residual               (annotation noise)
```

FiftyOne's `eval_key` per-sample fields + ARTIFEX jury routing directly implement this decomposition without a separate statistics package.

### Five Facets of Validity — Notebook Mapping

| Validity Facet | Notebook | Primary Instrument |
|---|---|---|
| **Content** | v7.2 (Spanish Benchmark) | `cultural_taxonomy.yaml` × BCP-47 coverage |
| **Construct** | v7.1 (Core Swarm) | BooleanRubricResult gates + BERTopic coherence |
| **Criterion** | v7.5 (FiftyOne Evaluation) | `evaluate_classifications()` + IRT θ̂ estimate |
| **External** | v7.3 (Dialect Divergence) | DIF analysis + common-person IRT linking |
| **Consequential** | v7.4 (Ethical Feedback Loop) | Time-horizon metric + propensity audit |

### Standards Alignment

| Standard | Version | ARTIFEX Implementation |
|---|---|---|
| NIST AI 800-3 | 2026 | GLMM variance decomposition, benchmark vs. generalized accuracy |
| ISO/IEC 42119-2 | Oct 2025 | Testing techniques across AI lifecycle |
| ISO/IEC 42119-3 | Oct 2025 | Verification & validation approaches |
| MLCommons AILuminate | 2026 | Structured risk assurance, BBOM supply-chain audit |
| BBOM (Benchmark Bill of Materials) | Layer 1–10 | All 11 pipeline rubric gates |

---

## What's New — v7.5 FiftyOne Model Evaluation

### ⓪ v7.5 FiftyOne Model Evaluation

Full `fiftyone` evaluation pipeline with:
- `evaluate_classifications("predictions", gt_field="ground_truth", eval_key="eval_simple")` — multiclass safety evaluation
- Binary evaluation (`safe` vs `unsafe`) with PR curves
- Per-sample correctness fields (`eval_simple` boolean per sample)
- Confusion matrix (normalized, dark-theme seaborn)
- Scenario analysis by language and hazard category
- IRT item characteristic curves (ICC) for item-level diagnostics
- BBOM compliance gate as a `BooleanRubricResult`

---

## Architecture Details

### ① Global Config (Cell 01) — Rubric Infrastructure

```python
@dataclass
class BooleanRubricResult:
    name: str       # machine-readable gate name
    passed: bool    # the only thing routing logic reads
    confidence: float
    escalate: bool
    severity: str   # HIGH / MEDIUM / LOW / INFO
    reason: str
    evidence: dict  # all raw values that drove the decision

RUBRIC_LOG = []     # append every rubric; dumped in Cell 13 audit
```

Thresholds defined once, used everywhere:
`MIN_ITEMS_BERTOPIC=500`, `MIN_HUMAN_CAL_ITEMS=30`,
`MIN_SILHOUETTE=0.10`, `MAX_SOFT_OVERLAP_FOR_AUTO=0.35`,
`DISAGREEMENT_ROUTE_COUNT=1`, `DENOM_EPS=0.05`

---

### ② Data Ingestion (Cell 02) — BBOM Layer 9 + Pandera Schema

- `region`, `language_code`, `cultural_context` columns added to synthetic data
- Pandera `FEEDBACK_SCHEMA` validates all ingested frames at runtime
- Three new rubrics emitted immediately after load:

```
  dataset_size_sufficient      →  n ≥ 500 for BERTopic/HDBSCAN
  coverage_metadata_present    →  region + language_code + cultural_context
  dialect_validated            →  ≥20% of items carry non-empty cultural_context
```

---

### ③ Embeddings (Cell 04) — Dual-Encoder Ensemble

```
  ┌─────────────────────────────────────────────────────┐
  │  EMBED_MODE = "ensemble"                            │
  │                                                     │
  │  [RoBERTuito]           [multilingual-E5-Large]     │
  │  social-text Spanish    1024-dim retrieval          │
  │  500M tweet corpus      multilingual semantic sim   │
  │        │                        │                   │
  │        └──────── hstack ────────┘                   │
  │               L2-normalize                          │
  │         fused embedding vector                      │
  └─────────────────────────────────────────────────────┘
```

Rubric: `embedding_ensemble_ready` — falls back gracefully to single-encoder
with severity=LOW (prototyping acceptable, production prefers ensemble).

---

### ④ Clustering (Cell 05) — HDBSCAN Soft Memberships

- `prediction_data=True` + `all_points_membership_vectors()` for per-point soft cluster scores
- Per-row columns: `cluster_soft_max`, `cluster_soft_entropy`, `cluster_soft_gap`
- `cluster_soft_gap < MAX_SOFT_OVERLAP_FOR_AUTO` → ambiguous boundary → route to HITL
- Cluster method auto-selected: `"leaf"` (n<250) vs `"eom"` (n≥250)

Rubrics:
```
  soft_membership_available    →  membership matrix shape matches df
  cluster_stability_sufficient →  silhouette ≥ MIN_SILHOUETTE
```

---

### ⑤ Swarm Routing (Cell 06) — Jury Voting Replaces Entropy Threshold

Old routing (brittle):
```python
if entropy > 0.9: route = "ROUTED_TO_HUMAN"
```

New routing (auditable):
```python
jury  = jury_vote(verdicts)          # counts unsafe/safe/abstain votes
route, jury_rubric, veto_rubric = route_item(jury, soft_gap, ontological_veto)
# → ONTOLOGICAL_VETO | ROUTED_TO_HUMAN | UNSAFE | SAFE
```

Every item now carries `jury_disagreement` and `soft_gap` in `results_df`.
BBOM Layer 1/3 `ontological_veto_triggered` marks category-mismatch failures
before they contaminate downstream metrics.

---

### ⑥ LLM-as-Judge (Cell 07) — Bias-Corrected Estimator

Calibration rubrics gate all accuracy claims:

```python
# Only claim "calibrated accuracy" when BOTH pass:
human_calibration_present   →  n_calibration ≥ MIN_HUMAN_CAL_ITEMS
judge_bias_correctable      →  |q1 - (1 - q0)| > DENOM_EPS

# Bias-corrected point estimate (Zheng et al., arXiv:2503.23339):
θ̂ = (p̂ - (1 - q₀)) / (q₁ - (1 - q₀))
```

If either rubric fails, the notebook outputs an uncalibrated disclaimer
and routes reporting to human-only.

---

### ⑦ HITL (Cell 11) — Triplet Active Learning Queries

Replaces single cosine-threshold exemplar with information-rate-aware
triplet selection (Beyond Labels, arXiv:2602.15738):

```
  Candidate set (ROUTED_TO_HUMAN items)
         │
  pairwise_distances(cosine)
         │
  sort by gap = |d(anchor,near) - d(anchor,far)|
         │
  top-k triplets  →  annotator sees (anchor, near, far)
         │
  rubric: active_learning_triplets_available
```

---

### ⑧ Environment Audit (Cell 13) — Full Rubric Log + BBOM Claim Gates

Cell 13 now renders the complete `RUBRIC_LOG` table and applies
BBOM stop-conditions before emitting any benchmark claim:

```
  can_claim_calibrated_accuracy  =  human_calibration_present
                                  AND judge_bias_correctable

  can_claim_benchmark_validity   =  dataset_size_sufficient
                                  AND coverage_metadata_present
                                  AND cluster_stability_sufficient

  BBOM_L1_L3_L8_L9_L10_clear    =  no HIGH-severity rubric failure
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
| **Audit** | RUBRIC_LOG + BBOM claim gates | Full run dumped in Cell 13 |

---

## Paper Review

A detailed critical review of two 2026 benchmark survey papers — covering Agent-as-a-Judge frameworks, contamination-resistant benchmarks (KAMI), multimodal cultural evaluation (Afri-MCQA, AVMeme Exam), adversarial robustness (CAIA), and agentic SDLC evaluation (DevOps-Gym) — is available in [`PAPER_REVIEW.md`](./PAPER_REVIEW.md).

---

## Annotation Guideline

The **Cultural Appropriateness Annotation Guideline v1.0** provides the master rubric and decision framework for evaluating AI model responses across multilingual and multicultural contexts. It includes:

- A two-step rating protocol (appropriateness label + harm severity scale 1–5)
- A ten-dimension cultural taxonomy
- A 50-item master Boolean rubric (5 items per dimension)
- Decision trees and routing rules for borderline cases
- Quality assurance procedures with IRR targets
- Ethical labor provisions for annotators

Full guideline: [`ANNOTATION_GUIDELINE.md`](./ANNOTATION_GUIDELINE.md)

---

## Future Work & Roadmap (v7.4+)

| Area | Enhancement | Rationale |
|---|---|---|
| **Dataset Scale** | Integrate public HuggingFace safety datasets (≥500 items) | Unblocks `dataset_size_sufficient` rubric for production claims |
| **Calibration** | Collect ≥30-item human calibration set | Unblocks `human_calibration_present` for bias-corrected judge |
| **Topic Quality** | Add gensim C_V coherence + topic diversity rubrics | Replaces silhouette proxy with semantically grounded gates |
| **Entropy Routing** | Monte Carlo Dropout uncertainty | Complement jury voting with epistemic uncertainty estimates |
| **Red-Teaming** | Automated adversarial pipeline | Continuous stress-test of swarm + KAMI contamination resistance |
| **X-Value Audit** | Domain expansion + drift tracking | Data sovereignty, algorithmic accountability, Consensus/Pluralism drift |
| **Speech Track** | Audio modality benchmarking | Swahili, Yoruba, Hausa, Arabic dialects (Afri-MCQA finding) |
| **Context Rot** | Routing consistency vs. turn index | Quantify degradation onset in long conversations |
| **Escalation Metric** | HITL validation rate | True-positive escalation vs. false ROUTED_TO_HUMAN rate |

---

## Research References

| Paper | Venue | Link |
|---|---|---|
| Benchmark Bill of Materials (BBOM) | 2026 | Supply-chain framing for benchmark validity |
| Adaptive Precise Boolean Rubrics | Google 2025 | [arXiv:2503.23339](https://arxiv.org/abs/2503.23339) |
| Bias-Corrected LLM-as-Judge | arXiv 2025 | [arXiv:2503.23339](https://arxiv.org/abs/2503.23339) |
| X-Value Cross-Lingual Values | Alibaba/ZJU 2026 | [arXiv:2602.17283](https://arxiv.org/abs/2602.17283) |
| Beyond Labels HITL | Georgia Tech 2026 | [arXiv:2602.15738](https://arxiv.org/abs/2602.15738) |
| Bangla Annotator Bias | Wichita State 2026 | [arXiv:2602.16241](https://arxiv.org/abs/2602.16241) |
| LPP Entropy Routing | AAMAS 2026 | [arXiv:2601.07006](https://arxiv.org/abs/2601.07006) |
| Omni-Safety | Feb 2026 | [arXiv:2602.10161](https://arxiv.org/abs/2602.10161) |
| Multi3Hate | NAACL 2025 | [arXiv:2411.03888](https://arxiv.org/abs/2411.03888) |
| Afri-MCQA | arXiv Jan 2026 | [arXiv:2601.05699](https://arxiv.org/abs/2601.05699) |
| AVMeme Exam | arXiv Jan 2026 | [arXiv:2601.17645](https://arxiv.org/abs/2601.17645) |
| Agent-as-a-Judge Survey | arXiv Jan 2026 | [arXiv:2601.05111](https://arxiv.org/abs/2601.05111) |
| CAIA Adversarial Benchmark | arXiv Oct 2025 | [arXiv:2510.00332](https://arxiv.org/abs/2510.00332) |
| LOCA-bench Context Growth | arXiv Feb 2026 | [arXiv:2602.07962](https://arxiv.org/abs/2602.07962) |
| DevOps-Gym SDLC Benchmark | arXiv Jan 2026 | [arXiv:2601.20882](https://arxiv.org/abs/2601.20882) |
| Gaia2 Dynamic Environments | arXiv Feb 2026 | [arXiv:2602.11964](https://arxiv.org/abs/2602.11964) |
| Aetheria Governance | Dec 2025 | [arXiv:2512.02530](https://arxiv.org/abs/2512.02530) |
| International AI Safety Report | PR Newswire 2026 | [Link](https://www.prnewswire.com/news-releases/2026-international-ai-safety-report-charts-rapid-changes-and-emerging-risks-302679401.html) |

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
