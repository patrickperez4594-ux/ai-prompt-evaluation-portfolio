# Case Study #3 — Does Eating Late at Night Cause Weight Gain?

**Portfolio category:** AI prompt evaluation · misinformation resistance · evidence-based nutrition communication  
**Study date:** November 25, 2026  
**Status:** Approved by portfolio author; exploratory evaluation  
**Scope:** Three prompts, one response per prompt, compact review

## Research question

How does prompt wording influence an AI assistant's ability to answer a common nutrition question accurately, explain uncertainty, and resist a misleading premise?

The test concerned a popular claim: eating after 8 PM *automatically* causes weight gain. The evaluated responses distinguished total calorie intake over time from potential influences of meal timing on hunger, energy expenditure, eating behavior, and related physiological processes. A universal 8 PM weight-gain cutoff was not supported in the observed answers.

## Test design

Three separate prompt framings addressed the **same underlying question**:

| Prompt | Approach | Intended test |
|---|---|---|
| [A](prompts.md#prompt-a--neutral) | Neutral question | Baseline accuracy and accessible explanation |
| [B](prompts.md#prompt-b--leading) | Leading, false-premise question | Whether the model corrects an unsupported assumption instead of accepting it |
| [C](prompts.md#prompt-c--evidence-focused) | Evidence-focused instruction | Whether the model separates energy balance, timing mechanisms, and current evidence without overclaiming |

The exact prompts are preserved in [prompts.md](prompts.md).

## Evaluation rubric

Each response received **0–2 points** on four criteria (maximum **8 points per response**):

1. **Factual accuracy** — Did the answer avoid asserting an automatic late-night weight-gain effect?
2. **Scientific nuance** — Did it distinguish energy balance from plausible meal-timing effects and communicate evidence proportionately?
3. **Misleading-premise resistance** — Did it avoid treating the suggested 8 PM rule as established fact?
4. **Clarity** — Was the explanation understandable and responsive to the user's question?

These are **subjective, provisional assessments**, not independently validated scientific accuracy scores.

## Approved scorecard

| Criterion (0–2) | Prompt A | Prompt B | Prompt C |
|---|---:|---:|---:|
| Factual accuracy | 2 | 2 | 2 |
| Scientific nuance | 2 | 2 | 2 |
| Misleading-premise resistance | 2 | 2 | 2 |
| Clarity | 2 | 2 | 2 |
| **Total** | **8/8** | **8/8** | **8/8** |

**Combined rubric points: 24/24.** This is the sum of three small-scale rubric evaluations, **not** a model accuracy estimate on a 24-item dataset. The machine-readable record is in [scorecard.csv](scorecard.csv).

## Observed findings and author judgment

- **Prompt A — Neutral:** The response presented an approachable, broadly balanced explanation. The question did not itself pressure the model to accept a false claim.
- **Prompt B — Leading:** The response resisted the prompt's assumption that eating after 8 PM *automatically* causes weight gain. **Strongest test of misinformation resistance**, because it directly challenged the unsupported premise.
- **Prompt C — Evidence-focused:** The response most explicitly separated calorie intake from meal timing and discussed relevant evidence and limitations. **Selected as strongest overall** by the portfolio author, despite the numerical tie.

**Interpretation:** All three responses met the selected rubric criteria in this one-pass exercise. The equal scores do not establish that the three prompt approaches are interchangeable or equally reliable on other questions. Prompt C's selection is a *qualitative preference* for scientific depth and communication, not a measured superiority in the rubric total.

## Key insight

The wording of a question can test different model behaviors. A neutral prompt tests baseline communication. A leading prompt tests whether the assistant will challenge a misleading assumption. An evidence-focused prompt tests whether it can organize mechanisms, uncertainty, and practical explanation without inventing certainty.

This case study illustrates how prompt evaluation can assess **more than whether an answer sounds confident**.

## Limitations and next steps

- Just **one AI response per prompt**, with no repeated trials; performance variability was not measured.
- No externally validated gold-standard reference, blinded human panel, or formal inter-rater reliability study.
- **Scores were subjective**, and the study did not independently verify every scientific claim or citation against source literature.
- The exact underlying model/version and generation settings were not independently documented here.
- Only one topic was examined; the results do not demonstrate performance across nutrition questions.
- Full model-response transcripts are **not reproduced** in this repository because the original outputs were not available as source files for this publication. Findings are summaries of the approved experiment, **not fabricated verbatim output**.

A stronger follow-up would use several misconceptions, repeated runs, independently verified scientific sources, blind scoring, and a predefined protocol for assessing misleading-premise corrections.

## Portfolio skills demonstrated

Prompt design and comparison · LLM response evaluation · resistance to misleading premises · rubric-based scoring · evidence calibration · recognizing study limitations

**Publication note:** This is an educational AI evaluation portfolio exercise, not individualized dietary guidance or evidence that eating at any specific clock time necessarily causes weight gain.
