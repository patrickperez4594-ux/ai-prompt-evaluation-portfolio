# AI Nutrition Education: Prompt Evaluation and Refinement

**Portfolio case study | Prompt engineering · LLM evaluation · User-centered communication**

## Project overview

This beginner-level experiment compared three prompts asking an AI assistant to explain the health benefits of blueberries. The goal was to assess whether more deliberate instructions could improve the quality of beginner-facing nutrition education while preserving scientific accuracy.

**Research question:** Can a revised prompt communicate established nutrition facts, emerging evidence, and practical advice in a way that is accurate, accessible, and encouraging?

## My contribution and design rationale

After comparing the initial responses, I preferred the broad, affirmative framing in Prompt A. I was concerned that Prompt B's emphasis on research limitations *might* lead some readers to underestimate the value of a nutritious food. This was a hypothesis about reader interpretation, not a demonstrated effect on readers.

I developed Prompt C around three priorities:

1. **Scientific accuracy:** Distinguish established nutritional facts from emerging research.
2. **Encouraging communication:** Communicate uncertainty proportionately without exaggerating benefits or implying that nutritious foods are pointless.
3. **Practical usefulness:** Offer affordable, realistic ways to include the food in everyday meals.

The intended improvement was not to remove uncertainty, but to communicate it in a way that supports informed choices.

## Test prompts

### Prompt A — Basic control

> What are the health benefits of blueberries?

### Prompt B — Evidence-focused

> You are an evidence-focused nutrition educator. Explain the health benefits of blueberries to a beginner.
>
> Include:
> 1. Three key nutrients or beneficial compounds.
> 2. How each may support health.
> 3. A practical serving suggestion.
> 4. Any important limitations in the scientific evidence.
>
> Use clear language, distinguish established facts from emerging research, and avoid exaggerated medical claims. Keep the response under 200 words.

### Prompt C — Balanced nutrition educator

> You are a nutrition educator who communicates scientifically accurate information in a clear, encouraging, and practical way.
>
> Explain the health benefits of blueberries to someone with little nutrition knowledge.
>
> Follow these requirements:
>
> 1. Begin by explaining why blueberries are a nutritious food, using established nutritional facts.
> 2. Identify three important nutrients or beneficial compounds found in blueberries and explain their roles in health.
> 3. Distinguish well-established nutritional benefits from promising findings that still require additional human research.
> 4. Communicate scientific uncertainty accurately and proportionately. Do not exaggerate benefits or imply that uncertainty about specific outcomes makes blueberries an unhealthy or pointless choice.
> 5. Provide two affordable, practical ways to include blueberries in everyday meals.
> 6. Use supportive, nonjudgmental language without making medical promises.
>
> Keep the explanation between 150 and 200 words, using short paragraphs or bullet points suitable for beginners.

## Evaluation method

One AI-generated response per prompt was compared using five qualitative criteria, each scored from 1 (poor) to 5 (excellent). The scores below are **preliminary subjective assessments**, not validated benchmarks. The original responses for A and B were discussed in the project conversation; Prompt C's response was supplied directly for the final comparison. The same-model/settings condition was requested but not independently verified.

| Criterion | Prompt A | Prompt B | Prompt C |
|---|---:|---:|---:|
| Scientific accuracy | 4 | 4 | 4 |
| Communication of uncertainty | 3 | 5 | 5 |
| Encouraging, non-misleading tone | 5 | 4 | 5 |
| Practical nutrition guidance | 3 | 4 | 5 |
| Beginner accessibility | 4 | 5 | 5 |
| **Total** | **19/25** | **22/25** | **24/25** |

### Findings

- **Prompt A** offered broad nutrition information in an approachable, positive tone, but less concrete meal guidance.
- **Prompt B** more explicitly distinguished emerging findings from established nutrient functions, though its caution raised a concern about potential reader interpretation.
- **Prompt C** combined well-established nutrient roles, proportionate discussion of uncertainty, and two accessible meal suggestions. It received the highest score under the revised rubric.

**Instruction-following note:** Prompt C appears to exceed its 150–200-word target. Word-count compliance was not included in the five-category rubric and should be measured separately in a follow-up test.

## Independent evaluator judgment

My final preference was **Prompt C**. I valued its balanced presentation: it describes blueberries as a nutritious food that can fit into a healthy dietary pattern while acknowledging that research on some specific long-term outcomes remains incomplete. In my view, this helps avoid confusing uncertainty about particular health claims with uncertainty about the food's basic nutritional value.

The established presence of fiber, vitamin C, and other compounds does not establish that blueberries alone prevent or treat disease. Individual allergies and dietary needs can also matter.

## Limitations and future work

- One food topic and one response per prompt; results cannot establish generalizable performance.
- No reader study was conducted, so the hypothesis that Prompt B could discourage readers remains untested.
- Scores were qualitative and assigned by an AI assistant; no independent blinded raters or inter-rater reliability checks.
- A source-by-source verification of every health claim was not completed.
- Different prompt requirements complicate a strict comparison of instruction-following.
- A follow-up should use repeated generations, identical model/settings, an explicit word-count check, cited nutrition sources, and blinded human ratings across multiple foods.

## Skills demonstrated

Prompt iteration; qualitative response evaluation; rubric design; evidence calibration; user-centered communication; documenting assumptions and limitations.

## Status

**Case study published as an exploratory portfolio report; follow-up validation remains recommended.** This is a learning portfolio exercise, not clinical nutrition guidance or proof of causal effects on reader behavior.