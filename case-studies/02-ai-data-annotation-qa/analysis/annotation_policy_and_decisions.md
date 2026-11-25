# Working Annotation Policy and Adjudication Log

**Status:** Provisional working policy, updated 2026-11-19. The study does **not** claim an independently adjudicated gold standard.

## Core sentiment interpretation

- **Positive:** explicit praise or reasonably supported favorable experience; mere completion of a routine expected process alone need not count as praise.
- **Negative:** a meaningful problem, criticism, poor outcome, or clear discouragement.
- **Neutral:** a fact or adequacy statement without sufficient evidence of endorsement or criticism.
- **Mixed:** meaningful positive **and** negative aspects. A phrase that simply acknowledges expected service may not constitute the positive side.

## Confirmed author adjudication: S06

> Support apologized immediately, but the replacement item failed too.

- All three model variants predicted **Mixed**.
- Portfolio author decided **Negative**, on the grounds that an apology without resolution is not a meaningful positive observation.
- The negative experience remains: the replacement failed.
- The **sentiment decision is confirmed**. The primary topic (**Customer Support**) remains provisional, because **Product Quality** is also plausible. Changing the topic would alter reported topic agreement.
- In this working reference set, **S06 = Negative / Customer Support**.

## Proposed (not independently confirmed) adjudications

- **S02:** Neutral / Product Quality — "loud enough" indicates adequacy, not clear satisfaction.
- **S04:** Neutral / Billing — arriving on the promised date does not itself express satisfaction.
- **S12:** Mixed / Product Quality — the review positively describes working well and negatively criticizes a useless manual. The inclusion of manuals within Product Quality is a working policy choice.
- **S09:** Negative / Other — no specific characteristic is identified, though Product Quality may be argued.
- **S10:** Negative / Other — checkout usability is not explicitly one of the four specialized topics; a broad Billing policy could differ.
- **R01:** Positive / Delivery — early delivery is treated as a favorable outcome under the provisional policy; stricter readings might choose Neutral.
- **R09:** Mixed / Billing — correct refund processing plus a lengthy delay was provisionally treated as Mixed; a stricter policy that treats routine processing as neutral could instead choose Negative. This potential inconsistency must be resolved before any gold-standard claim.
- **R11:** Neutral / Product Quality — "works as advertised; nothing special" does not clearly signal praise.

## Topic priority and consistency

- Exactly one primary topic per review.
- Shipping fees billed contrary to promise: **Billing**, not Delivery (S07).
- Checkout functionality: **Other** in this working policy (S10).
- General nonrecommendation with no specified attribute: **Other** (S09).
- Multi-topic reviews require a documented priority rule. S06 is currently **Customer Support** as predicted by all prompts, but that topic choice has *not* been independently adjudicated.
- Product documentation: **Product Quality** in this working policy (S12), pending confirmation.

## Status and methodological note

The author explicitly confirmed **only the S06 sentiment ruling** in this step. All other reference labels were produced during the earlier analysis and remain provisional. Agreement metrics are conditional on this working set. A future blinded second annotator and formal adjudication would improve validity.
