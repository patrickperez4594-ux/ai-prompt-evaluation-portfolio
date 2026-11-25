# AI Data Annotation & Quality Assurance — Case Study #02

An exploratory evaluation of three prompting strategies for classifying customer-review **sentiment** and **primary topic**, using two 12-item synthetic datasets.

## At a glance

- **6 runs**: A (basic), B (detailed guidelines), C (guidelines + structured QA), each on V1 and challenge V2.
- **24 synthetic reviews**; **72 total model predictions**.
- **V1:** All three prompts matched the provisional sentiment and topic references (12/12 for each).
- **V2:** Sentiment agreement with the working references: **A 10/12**, **B 11/12**, **C 11/12**. Topic agreement: **12/12** each (topics are provisional).
- **Confirmed human decision:** S06 sentiment is **Negative**, not the **Mixed** predicted by all three prompts.
- **Caution:** All other reference labels are provisional, so these figures are working-set agreement, **not validated real-world accuracy**.

**Read the full study:** [CASE_STUDY.md](CASE_STUDY.md)  
**Reference policy:** [analysis/annotation_policy_and_decisions.md](analysis/annotation_policy_and_decisions.md)

## Repository structure

```text
CASE_STUDY.md
README.md
data/
  reviews.csv
  working_reference_labels.csv
results/
  model_predictions.csv
  working_reference_scores.csv
prompts/
  V1_prompt_A.txt
  V1_prompt_B.txt
  V1_prompt_C.txt
  V2_prompt_A.txt
  V2_prompt_B.txt
  V2_prompt_C.txt
analysis/
  annotation_policy_and_decisions.md
```

## Ethical note

All reviews are fictional. Model outputs were observed in user-run ChatGPT tests. This report does not claim a fully blinded adjudication or generalizable model superiority. No screenshot containing phone UI has been included.