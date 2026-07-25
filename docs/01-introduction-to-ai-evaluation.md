# 01 · Introduction to AI Evaluation

## What "AI evaluation" actually means

AI evaluation is the practice of systematically judging the quality of an AI system's output against a defined standard, so that judgment can be trusted, compared, and acted on.

That definition has three parts worth separating, because each one fails in a different way if you skip it:

| Part | What it means | What happens if you skip it |
|---|---|---|
| **Systematic** | You follow a repeatable process, not a mood | Scores swing with your energy level, not the response quality |
| **Defined standard** | You're comparing against a rubric, not a vibe | Two evaluators disagree and neither can explain why |
| **Trusted / actionable** | The output feeds a decision (train the model differently, block a release, flag a bug) | Evaluation becomes busywork instead of a feedback loop |

Evaluation is not the same as "reading the response and reacting to it." Reacting is instant and personal. Evaluating is deliberate and structured — it asks *specific* questions in a *specific* order and records the answers so someone else could check your work.

## Why evaluation is hard

Three things make it harder than it looks:

1. **Fluency looks like correctness.** A confidently written, well-formatted, grammatically clean answer *feels* trustworthy even when it's factually wrong. Evaluators have to actively resist this — check the substance separately from the polish.
2. **"Good" is multi-dimensional.** A response can be accurate but rude, helpful but unsafe, safe but useless. Single-number gut scores collapse these dimensions and hide the actual problem.
3. **Context changes the bar.** The same response can be excellent for one user and inappropriate for another (e.g., technical depth for an expert vs. a beginner). Evaluation has to account for the implied audience and intent, not just the words on the page.

## The evaluator's core loop

Every evaluation, no matter the format, follows roughly this loop:

1. **Understand intent** — What was the user actually trying to accomplish? What would "success" look like from their side?
2. **Read the response fully** — Resist scoring after the first paragraph. Problems often show up at the end (an unsafe suggestion buried in an otherwise fine answer, a contradiction between the intro and the conclusion).
3. **Check against each dimension separately** — Accuracy, helpfulness, safety, tone, formatting — one at a time (see `02-evaluation-dimensions.md`).
4. **Identify specific evidence** — Point to the sentence or claim that supports each judgment. "It felt off" is not evidence. "The response claims X, which contradicts source Y" is.
5. **Assign a score using the rubric** — Not your personal preference; the standard the task defines (see `03-rubrics-and-scoring-scales.md`).
6. **Write the reasoning down** — The written justification is often more valuable than the score itself, because it's what makes the evaluation reproducible and useful for improving the system.

## What makes an evaluation "expert-level"

Beginners score responses. Experts score responses **and** can explain, in specific and falsifiable terms, exactly why — in a way that would let another trained evaluator arrive at the same score independently. The rest of this repository is about building that second skill.

---
**Next:** [`02-evaluation-dimensions.md`](02-evaluation-dimensions.md)
