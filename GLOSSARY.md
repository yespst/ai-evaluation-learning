# Glossary

Terms used throughout this repository, defined precisely so they're used consistently.

**Anchor example** — A concrete, agreed-upon example attached to a specific point on a rubric scale, used to keep that score level's meaning stable across evaluators and over time.

**Calibration** — The process of checking an evaluator's scores against a known standard (an answer key, another evaluator, or their own past scores) to detect and correct drift.

**Comparative evaluation / Pairwise ranking** — Judging two responses to the same prompt against each other ("A vs. B"), rather than scoring each in isolation.

**Dimension** — A single, independently-gradable axis of quality (e.g., helpfulness, accuracy, safety, tone). See `docs/02-evaluation-dimensions.md`.

**Error taxonomy** — A categorized list of failure types (hallucination, over-refusal, tone mismatch, etc.) used to classify what specifically went wrong in a response, rather than just how badly.

**Evaluator drift** — The gradual, unconscious loosening or tightening of an evaluator's internal standard over time or across a long evaluation session.

**Failure mode** — A named, recognizable pattern of response failure (e.g., "sycophancy," "under-refusal") that generalizes across many individual examples.

**Halo/horn effect** — The tendency for one strong (halo) or one glaring (horn) quality in a response to bias the perceived quality of unrelated dimensions.

**Hallucination** — Content presented as fact that is fabricated, unverifiable, or not actually supported by any real source, despite being stated with apparent confidence.

**Inter-rater agreement** — The degree to which independent evaluators arrive at the same or similar scores for the same response; a core measure of whether a rubric is actually well-specified.

**Over-refusal** — Declining to help with a request that was, on inspection, benign and reasonable — a genuine quality failure, not a "safe default."

**Position bias** — In pairwise comparisons, a systematic tendency to favor whichever response is shown first (or last), independent of content.

**RLHF (Reinforcement Learning from Human Feedback)** — A model training technique that uses human preference judgments (often pairwise comparisons) as a training signal to shape model behavior.

**Rubric** — A defined, written standard used to score a response, including the dimensions being measured, the scale, and anchor examples for each level.

**Sycophancy** — A response that shifts its factual position or judgment to match a user's expressed opinion rather than the evidence.

**Under-refusal** — Complying with a request that should have been declined on safety grounds, including cases where a lightly reworded harmful request is granted.
