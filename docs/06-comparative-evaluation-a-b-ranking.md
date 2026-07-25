# 06 · Comparative Evaluation (A/B Ranking)

A large amount of real-world AI evaluation work — especially in model training pipelines like RLHF (Reinforcement Learning from Human Feedback) — takes the form of "here are two responses to the same prompt, which is better, and why?" This document covers that format specifically.

## Why comparative evaluation is used so heavily

Absolute scoring (rate this response 1–5) requires the evaluator to hold an internal, stable standard of what "3" means. That standard drifts easily (see `05-bias-and-consistency.md`). Comparative evaluation sidesteps this: humans are reliably better at judging *relative* quality ("A explains this more clearly than B") than *absolute* quality ("this explanation is a 4 out of 5"). It also maps directly onto how model training uses the signal — as a preference, not a score.

## The method

1. **Read the prompt first, alone.** Form your own idea of what a strong response would need to include before looking at either candidate — this stops the first response you read from anchoring your standard.
2. **Read Response A fully. Then read Response B fully.** Don't skim-compare paragraph by paragraph on a first pass; each response deserves an independent read before you start contrasting them.
3. **Score each dimension for A and B separately** (helpfulness, accuracy, safety, tone, etc. — see `02-evaluation-dimensions.md`), rather than jumping to a single overall winner.
4. **Identify the deciding dimension(s).** Two responses are rarely tied on everything. Name specifically where they diverge and why that divergence matters for this particular prompt.
5. **Make the call**, using one of:
   - **A is clearly better**
   - **B is clearly better**
   - **A is slightly better**
   - **B is slightly better**
   - **Tie / both inadequate** (use sparingly — genuine ties are rarer than they feel, and "both inadequate" is a real, useful signal, not an escape hatch)
6. **Write the reason as a comparison, not two separate reviews.** "A correctly explains the tax implication that B omits entirely" is a comparison. "A is good. B is also pretty good." is not.

## Handling position bias

Since order effects are well-documented (see `05-bias-and-consistency.md`), when the stakes are high or you're uncertain, deliberately re-run the comparison with the responses in the opposite order and see if your verdict holds. If it flips, you weren't actually judging content — you were judging position, and you need to look again.

## Common ranking traps

| Trap | Why it's a trap |
|---|---|
| **Rewarding length as thoroughness** | A longer answer isn't automatically more complete — check whether the extra length is adding real content or padding |
| **Rewarding hedging as honesty** | Excessive caveats can *look* more careful while actually being less useful; genuine honesty is calibrated, not maximally hedged |
| **Penalizing correct brevity** | If the prompt was simple, a short correct answer should beat a long correct one, not lose to it |
| **Letting one severe flaw in an otherwise-strong response hide a fatal flaw in the other** | Rank each dimension, don't let overall "vibes" of A dominate a real defect in B that you didn't check closely because A already "won" |

## Worked example (abbreviated)

> **Prompt:** "My unit test for this function keeps failing intermittently. Here's the code. What's going on?"
>
> **Response A:** Identifies a race condition in shared mutable state, explains the mechanism, and provides a corrected version using a lock.
>
> **Response B:** Suggests re-running the test suite and checking for flaky CI infrastructure, without examining the code's logic.

- **Helpfulness:** A directly solves the stated problem. B offers a generic troubleshooting step that doesn't engage with the actual code. **A wins.**
- **Accuracy:** A's diagnosis is technically correct given the shared state pattern in the code. B's suggestion isn't wrong in general, but doesn't address *this* case. **A wins.**
- **Verdict: A is clearly better** — A engages with the specific mechanism causing the bug; B gives generic advice that would apply to almost any flaky test, regardless of cause.

---
**Previous:** [`05-bias-and-consistency.md`](05-bias-and-consistency.md) · **Back to:** [`../README.md`](../README.md)
