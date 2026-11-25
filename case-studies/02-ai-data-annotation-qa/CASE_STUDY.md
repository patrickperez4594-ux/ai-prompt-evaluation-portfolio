# Case Study #2 — AI Data Annotation & Quality Assurance

**Project:** Evaluating customer-review sentiment and topic classification with increasingly detailed prompts  
**Date:** November 19, 2026  
**Study type:** Exploratory, retrospective, small-sample prompt comparison  
**Dataset:** 24 synthetic reviews, divided into an initial 12-item dataset (V1) and a 12-item challenge set (V2)  
**Runs:** Six ChatGPT conversations (Prompts A, B and C tested once on each dataset)  
**Model:** ChatGPT; exact underlying model/version, temperature, and random seed were not captured and therefore cannot be independently specified  
**Status:** Portfolio case study complete as a *provisional evaluation*, **not** an independently validated benchmark.

## Executive summary

I compared three approaches to labeling fictional customer feedback: a basic classification prompt (A), a guideline-rich prompt (B), and a prompt with explicit human-review flags and structural QA (C). All six runs returned 12 complete reviews with valid labels and no observed duplicate IDs. The original V1 dataset yielded the same 12 sentiment and 12 topic labels for all three approaches. On a harder V2 dataset, Prompt A classified one review differently from B and C: an on-time refund (S04) was Positive under A but Neutral under B and C.

I then applied a human judgment to review S06: a prompt apology followed by a failed replacement was classified **Mixed** by all models, but I adjudicated it as **Negative**, because an apology without resolution is not a meaningful positive outcome. With this ruling and the other still-provisional references, sentiment agreement on V2 was **10/12 (83.3%) for A** and **11/12 (91.7%) for B and C**. Topic agreement was **12/12 for all three**, subject to unresolved topic-priority decisions.

**Main takeaway:** Detailed instructions changed a borderline sentiment decision, and the QA prompt surfaced ambiguity explicitly. The experiment does *not* establish that Prompt C is objectively more accurate than B, nor that any method generalizes to larger datasets.

## Research question and hypothesis

**Question:** How do prompt specificity and quality-control instructions affect AI classification of customer reviews involving sarcasm, mixed sentiment, factual descriptions, and ambiguous topics?

**Initial hypothesis:** More explicit labeling rules and output checks would produce more consistent and useful annotations than a minimal prompt.

## Method

1. Prepared two 12-review synthetic datasets (V1 and V2), each with four possible sentiment classes (Positive, Negative, Neutral, Mixed) and five possible primary topics (Delivery, Product Quality, Billing, Customer Support, Other).
2. Ran each dataset in three **fresh ChatGPT conversations** using separate prompt configurations. This reduced within-thread carryover, but does not guarantee independence across a shared service/model.
3. Preserved the review text and label taxonomy across prompt variants. Prompt instructions and output requirements changed by design.
4. Recorded the model outputs and checked completeness, duplicates, and valid labels.
5. Compared outputs with a **working reference-label set**, not a blinded or independently adjudicated gold standard. After seeing outputs, the portfolio author formally adjudicated S06 sentiment as Negative.
6. Calculated exact-match agreement separately for sentiment, topic, and both labels together.

### Prompt variants

| Variant | Instruction strategy | Explicit per-row human-review column? |
|---|---|---|
| A | Basic classification request | No |
| B | Definitions, sarcasm/mixed guidance and explanation requirement | No |
| C | Detailed definitions, ambiguity flags, post-output QA checks | Yes |

The full six prompts are under `prompts/`.

## Observed results

| Dataset | Prompt | Sentiment matches | Topic matches | Joint review matches |
|---|---|---:|---:|---:|
| V1 | A | 12/12 (100.0%) | 12/12 (100.0%) | 12/12 |
| V1 | B | 12/12 (100.0%) | 12/12 (100.0%) | 12/12 |
| V1 | C | 12/12 (100.0%) | 12/12 (100.0%) | 12/12 |
| V2 | A | 10/12 (83.3%) | 12/12 (100.0%) | 10/12 |
| V2 | B | 11/12 (91.7%) | 12/12 (100.0%) | 11/12 |
| V2 | C | 11/12 (91.7%) | 12/12 (100.0%) | 11/12 |
| Both sets | A | 22/24 (91.7%) | 24/24 (100.0%) | 22/24 |
| Both sets | B | 23/24 (95.8%) | 24/24 (100.0%) | 23/24 |
| Both sets | C | 23/24 (95.8%) | 24/24 (100.0%) | 23/24 |

**Interpretation:** All accuracy-like percentages are **conditional agreement with a working label set**. They should not be represented as independently confirmed ground-truth accuracy. The perfect V1 values indicate a likely ceiling effect, not perfect general reliability.

### V2 disagreement analysis

| Review | A | B | C | Working reference | Finding |
|---|---|---|---|---|---|
| S04 — refund arrived on promised date | Positive | Neutral | Neutral | Neutral (provisional) | A treats expected refund timing as favorable; B/C avoid inferring praise |
| S06 — immediate apology; failed replacement | Mixed | Mixed | Mixed | **Negative (author adjudicated)** | All variants treat apology as meaningful positive evidence; author's policy requires meaningful resolution/positive experience |

All other V2 sentiment predictions matched each other and the working reference. All V2 topic predictions matched each other and the *provisional* topic set.

### Human-review and QA behavior

- **V1 Prompt C:** flagged R01, R09 and R11 (3/12) for potential human adjudication.
- **V2 Prompt C:** flagged S02, S04, S06 and S12 (4/12), with explicit Yes/No values per row.
- **V2 Prompt B:** discussed potential human review for S02, S04, S06 and S10 in its narrative QA section, despite no required per-row flag field.
- **V2 Prompt A:** identified S02, S06, S09 and S12 as potential annotation disagreements in its narrative notes, although the basic prompt did not ask for review flags.
- Across all six outputs: no missing records, duplicate IDs, invalid sentiment classes, invalid topic classes, or multi-topic assignments were observed.

**Important limitation:** Prompt C's more structured flagging reflects an explicit output-format requirement, so it is not proof that C alone can recognize ambiguity. The other prompts also discussed uncertainty.

## Human adjudication log — S06

**Review:** “Support apologized immediately, but the replacement item failed too.”  
**Predictions:** A = Mixed, B = Mixed, C = Mixed.  
**Author's decision:** **Negative sentiment.**  
**Rationale:** An immediate apology without an effective resolution does not, by itself, establish a meaningful positive customer experience. The subsequent replacement failed.  
**Status:** Sentiment adjudicated; primary topic **Customer Support** remains provisional because **Product Quality** is also plausible.  
**Effect on results:** All three variants have a sentiment disagreement with the adjudicated S06 label.

## Interpretation and recommendations

1. **Document the unit of evaluation.** Report sentiment and topic separately; the same review may have a defensible topic classification but a disputed sentiment.
2. **Define positive evidence more tightly.** Disambiguate routine expected outcomes (S04), adequate performance (S02), apologetic responses without resolution (S06), and documentation quality (S12).
3. **Add topic-priority rules.** Explicitly cover multi-domain experiences such as a failed replacement handled by support and website checkout problems.
4. **Keep an escalation path.** Review flags and adjudication comments prevent potentially subjective labels from silently being treated as settled truth.
5. **Do not claim an accuracy victory prematurely.** Prompt B and C have identical labels in V2, and the apparent advantage versus A is based on one provisional judgment (S04), not repeated trials.

## Limitations

- **Only 24 fictional examples** and one run per prompt/dataset; no confidence intervals or statistical significance claims.
- **Post-hoc reference set:** most references were formulated or reviewed after model results; only S06 sentiment was explicitly adjudicated by the portfolio author at finalization.
- **Ambiguity remains:** R01, R09, R11, S02, S04, S12, S06 topic and some topic-priority choices need independent review. In particular R09's working Mixed label may conflict with a policy treating routine correct refunds as neutral.
- **No confirmed model pinning:** exact model/version and generation settings were not recorded; results are a snapshot, not a reproducible performance guarantee.
- **Instruction and output formats differ:** C was explicitly asked for review flags; format differences are not controlled independent of prompt changes.
- **No external-human inter-annotator reliability:** agreement with the working set cannot be equated with consensus.
- **No production claim:** synthetic reviews do not capture real-world distribution, multilingual inputs, or class imbalance.

## Next iteration

If expanded, recruit a second annotator to blind-label each review *before* showing model outputs; adjudicate the conflicts, freeze a reference set and policy, and test multiple runs on a larger held-out dataset with the same pinned model and sampling settings. Score accuracy, inter-annotator agreement, human-review precision/recall, and execution completeness separately.

## Artifacts and evidence

- `data/reviews.csv`: both datasets (24 unique review IDs).
- `data/working_reference_labels.csv`: provisional references and S06 author-adjudicated sentiment marker.
- `results/model_predictions.csv`: all 72 predicted review-level rows across six runs (transcribed from screenshots supplied in conversation for the original tests and V2 A, and pasted text for V2 B/C).
- `results/working_reference_scores.csv`: automatically computed working-set agreements.
- `prompts/`: prompt text for each variant and dataset.
- `analysis/annotation_policy_and_decisions.md`: policy details and confirmed vs provisional decisions.

**Provenance:** The original exchanges were performed by the portfolio author in ChatGPT and reported through screenshots or pasted outputs. The numeric scores and comparison tables here were recomputed from those reported outputs; raw screenshots are **not** included in this public-facing package to avoid unintentionally sharing phone UI or personal notifications.