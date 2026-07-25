# 05 · Bias and Consistency in Evaluation

An evaluator is also a measuring instrument, and instruments have known sources of error. This document names the biases that most commonly distort AI evaluation, so you can actively correct for them.

## Known evaluator biases

### Length bias
Longer responses are frequently rated as more helpful or thorough, independent of actual content quality. A padded, repetitive answer can outscore a tight, correct one purely on volume.
- **Correction:** Explicitly ask "what would I lose if this were half as long?" If the answer is "nothing," length was inflating the score.

### Style / fluency bias
Confident, well-formatted, grammatically polished text reads as more trustworthy, even when the underlying claims are wrong.
- **Correction:** Evaluate accuracy on a separate pass from tone/formatting, so polish doesn't bleed into the substance score.

### Position / order bias
In pairwise comparisons, the response shown first (or last) gets a slight, systematic edge regardless of content.
- **Correction:** Where possible, evaluate the same pair in both orders, or deliberately alternate which side you read first.

### Familiarity bias
A response that agrees with what the evaluator already believes gets rated as more "correct," independent of whether it's actually supported by evidence.
- **Correction:** For contested or opinion-adjacent topics, evaluate whether the response is *well-reasoned and well-sourced*, not whether you agree with its conclusion.

### Anchoring from the first dimension checked
Whichever dimension you evaluate first colors your read of every dimension after it (a strong opening on tone makes you more lenient on accuracy).
- **Correction:** Check the dimension most prone to being missed (usually accuracy or safety) *first*, before tone or style has a chance to color your judgment.

### Halo/horn effect
One strong or one glaring flaw dominates the overall impression and drags every other dimension's score toward it, even where they're unrelated.
- **Correction:** Score dimensions independently before computing or estimating any overall impression (see `02-evaluation-dimensions.md`).

### Fatigue drift
After evaluating many responses in a row, standards unconsciously loosen (easier to wave things through) or tighten (irritation compounds).
- **Correction:** Take breaks; periodically re-score a "known" calibration example to check your bar hasn't moved.

## Consistency techniques

| Technique | What it does |
|---|---|
| **Blind re-scoring** | Re-evaluate a past item without seeing your original score, then compare |
| **Inter-rater checks** | Have a second evaluator score the same item independently; investigate disagreements > 1 point |
| **Written justification requirement** | Force every score to come with a specific, quotable reason — vague reasoning is a sign the score itself is unreliable |
| **Calibration sets** | Maintain a small set of examples with agreed-upon "correct" scores; periodically re-score them to detect drift |
| **Dimension-first scoring** | Always score each dimension before forming an overall impression (never the reverse) |

## A useful mental discipline

Before finalizing any score, ask yourself:

> "If I gave this exact response, with no other context, to another trained evaluator and asked them to score it using the same rubric — would they land within one point of me? If not, what am I seeing that isn't actually written in the rubric?"

That question, asked honestly and often, is most of what separates a reliable evaluator from an inconsistent one.

---
**Previous:** [`04-common-failure-modes.md`](04-common-failure-modes.md) · **Next:** [`06-comparative-evaluation-a-b-ranking.md`](06-comparative-evaluation-a-b-ranking.md)
