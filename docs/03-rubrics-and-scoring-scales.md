# 03 · Rubrics and Scoring Scales

A rubric turns "judgment" into something measurable. This document covers the common scale types you'll encounter and how to use each one without letting it quietly become arbitrary.

## Common scale types

### 1. Binary (Pass / Fail)
Used when a response either meets a hard requirement or it doesn't — no middle ground.
- Good for: safety violations, format compliance ("must return valid JSON"), factual claims ("is the capital city named correctly?").
- Weakness: hides degrees of severity. A minor formatting slip and a dangerous safety failure both just read "Fail" unless you pair the scale with a severity note.

### 2. Likert scale (e.g., 1–5 or 1–7)
Used for graded quality dimensions like helpfulness or tone.
- A typical 5-point version:

| Score | Meaning |
|---|---|
| 1 | Actively harmful or unusable |
| 2 | Significant problems; barely usable without major rework |
| 3 | Adequate; meets the basic need but has clear room for improvement |
| 4 | Strong; minor nitpicks only |
| 5 | Excellent; meets or exceeds what a careful expert would produce |

- Weakness: evaluators drift toward the middle ("3 is safe") unless the anchors for each number are concretely defined *in advance*, with examples.

### 3. Pairwise / Comparative ranking (A vs. B)
Used when you're comparing two candidate responses rather than scoring one in isolation.
- Often easier and more reliable than absolute scoring — humans are much better at "which is better" than "how good is this on a scale of 1–5," because comparison doesn't require an internal anchor.
- Always pair with a **reason**: "A is better because it correctly handles the edge case B misses" — not just a preference.
- See `06-comparative-evaluation-a-b-ranking.md` for the full method.

### 4. Error taxonomy / checklist
Used when you want to catalog *what kind* of problem exists, not just how bad it is.
- Example categories: factual error, logical inconsistency, unsafe content, formatting violation, tone mismatch, incomplete answer, hallucinated citation.
- Strongest for feeding structured data back into model improvement — "12% of failures this week were hallucinated citations" is actionable in a way "average score was 3.4" is not.

## Anatomy of a good rubric

A rubric that actually produces consistent scores across different evaluators needs four things:

1. **A clear dimension name** — "Helpfulness," not "Quality" (too vague to check against).
2. **Anchor examples at each score level** — a real (or realistic) example of a 2 and a real example of a 4, so "adequate" isn't left to imagination.
3. **Explicit exclusions** — what this dimension is *not* judging (e.g., "Accuracy" should say "grammar issues don't affect this score, that's covered under Tone").
4. **A tie-breaking rule** — what to do when a response is excellent on one dimension and poor on another (does one dimension gate the others? Is there a weighted average? Is safety always a hard override?).

## Calibration: why your first 10 scores don't count yet

Before an evaluator's scores can be trusted, they need to be **calibrated** — checked against either a known-good answer key or another experienced evaluator's scores on the same items. This catches two common problems:

- **Severity drift** — over time, evaluators unconsciously loosen or tighten their bar (what used to be a 3 slowly becomes a 4).
- **Personal bias leakage** — favoring a particular writing style, length, or tone regardless of what the rubric actually asks for.

**Practical habit:** re-score a handful of your own past evaluations blind (without seeing your original score) every so often. If your new score disagrees with your old one by more than one point on a 5-point scale, your calibration has drifted and it's worth revisiting the rubric anchors.

---
**Previous:** [`02-evaluation-dimensions.md`](02-evaluation-dimensions.md) · **Next:** [`04-common-failure-modes.md`](04-common-failure-modes.md)
