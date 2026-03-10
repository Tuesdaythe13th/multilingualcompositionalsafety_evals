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
  ║  BBOM SUPPLY-CHAIN AUDIT  ·  LLM-AS-JUDGE  ·  FIFTYONE ANNOTATION          ║
  ╚══════════════════════════════════════════════════════════════════════════════╝
```

**Principal Investigator**: Tuesday, ARTIFEX Labs
**Branch**: `claude/adaptive-boolean-rubrics-lgx2v`

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

| Version | Open in Colab | Description |
|---|---|---|
| **v7.1** ★ | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/claude/adaptive-boolean-rubrics-lgx2v/ARTIFEX_v7_Compositional_Safety.ipynb) | **Core Multilingual Swarm** — Now with adaptive boolean rubrics, jury routing, dual-encoder embeddings, HDBSCAN soft memberships, calibrated LLM-as-judge, and triplet HITL queries. |
| **v7.4** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/master/ARTIFEX_v7.4_Ethical_Feedback_Loop.ipynb) | **Ethical Feedback Loop** — 2026 agentic benchmarking insights with feedback-loop analysis. |
| **v7.3** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/master/ARTIFEX_v7.3_Dialect_Divergence.ipynb) | **Dialect Divergence Benchmark** — Castilian vs. Mexican Spanish, 200-pair parallel corpus. |
| **v7.2** | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Tuesdaythe13th/multilingualcompositionalsafety_evals/blob/master/ARTIFEX_v7.2_Spanish_Benchmark.ipynb) | **Spanish Benchmark Edition** — 68-prompt Colombian-context benchmark with X-Value Radar charts. |

---

## Upgrade Details — `claude/adaptive-boolean-rubrics-lgx2v`

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

```
  ╔═══════════════════════════════════════════════════════════════╗
  ║  ARTIFEX LABS  ·  FOR RESEARCH PURPOSES ONLY                 ║
  ║  Tuesday  ·  2026  ·  claude/adaptive-boolean-rubrics-lgx2v  ║
  ╚═══════════════════════════════════════════════════════════════╝
```
