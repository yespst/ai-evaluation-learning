# 04 · Common Failure Modes in AI-Generated Responses

Knowing the *named* failure patterns makes them much faster to spot. This is a field guide — treat it as a checklist to run a response against.

## Content failure modes

| Failure mode | What it looks like | How to catch it |
|---|---|---|
| **Hallucination** | A confidently stated fact, citation, quote, or statistic that is fabricated or unverifiable | Ask: "Could I verify this against a real source right now?" If unsure, treat it as unverified, not true |
| **Outdated information** | Correct as of training data, but stale relative to the current date | Check anything involving "current," "latest," roles/positions, prices, or versions |
| **Overgeneralization** | A narrow or conditional truth stated as a universal rule | Look for absolute language ("always," "never," "all") applied to a genuinely mixed reality |
| **Sycophancy** | Agreeing with the user's stated belief or framing even when it's wrong, to avoid friction | Check: would the response say the same thing if the user hadn't hinted at their own opinion first? |
| **Non-answer** | Technically responds, but dodges the actual question (common in refusals-that-shouldn't-be-refusals, or vague hedging) | Ask: "If I only had this response, could I now do the thing I originally wanted to do?" |
| **Scope creep** | Answers a broader or different question than the one asked, padding length without adding value | Compare the response's content against the literal question asked |

## Reasoning failure modes

| Failure mode | What it looks like | How to catch it |
|---|---|---|
| **Non-sequitur conclusion** | The final answer doesn't actually follow from the stated steps | Re-derive the conclusion yourself from the stated premises only |
| **Silent assumption** | A step relies on something unstated and unjustified | Ask: "What would have to be true for this step to hold, and did the response say it?" |
| **Confirmation-shaped reasoning** | Steps are arranged to justify a predetermined answer rather than derive one | Check if any step, examined alone, would still be chosen if the conclusion were different |
| **Arithmetic/logical slip** | A correct method with an execution error partway through | Recompute or re-trace independently, don't just "look" for errors |

## Safety and policy failure modes

| Failure mode | What it looks like | How to catch it |
|---|---|---|
| **Under-refusal** | Provides operationally dangerous detail that should have been declined | Check against the specific harm categories relevant to the domain (weapons, malware, self-harm, exploitation) |
| **Over-refusal** | Declines a benign, reasonable request out of excess caution | Ask: "Would a thoughtful, non-paranoid professional actually see this as risky?" |
| **Partial leakage** | Refuses the direct ask but provides enough adjacent detail to reconstruct the harmful content anyway | Check whether the "safe" parts of the response, combined, still deliver the harmful payload |
| **Inconsistent boundary** | Refuses a request, then complies with a lightly reworded version with no real change in risk | Compare the refused and complied-with versions side by side |

## Communication failure modes

| Failure mode | What it looks like | How to catch it |
|---|---|---|
| **Wall of text** | Long, unstructured response where a shorter or more structured one would serve better | Ask: "Could this be 40% shorter without losing anything the user needed?" |
| **Over-formatting** | Headers, bold, and bullets used on a response that should just be a few plain sentences | Ask: "Does this read like a report when the user asked a conversational question?" |
| **False confidence** | Uncertain or contested information presented with unwarranted certainty | Check whether hedging language matches the actual reliability of the claim |
| **Tone mismatch** | Overly clinical response to an emotional topic, or overly casual response to a serious one | Re-read the prompt for emotional or situational cues the response should have picked up on |

## How to use this list in practice

Don't try to hold all eighteen patterns in your head while reading a response for the first time — that's how you end up skimming for problems instead of reading for understanding. Instead:

1. Read the response once, straight through, for comprehension.
2. Read it a second time with this table open, checking row by row.
3. Only mark a failure mode if you can point to the specific sentence or phrase that demonstrates it.

---
**Previous:** [`03-rubrics-and-scoring-scales.md`](03-rubrics-and-scoring-scales.md) · **Next:** [`05-bias-and-consistency.md`](05-bias-and-consistency.md)
