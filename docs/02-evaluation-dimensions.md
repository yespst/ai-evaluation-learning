# 02 · Evaluation Dimensions

A response is never "good" or "bad" as a single fact — it's good or bad *along several independent axes at once*. Splitting a judgment into dimensions is the single highest-leverage habit an evaluator can build, because it turns a fuzzy impression into a checklist.

## The six core dimensions

### 1. Helpfulness
Does the response actually move the user toward what they were trying to accomplish?
- Does it answer the question that was asked, not a nearby question that's easier to answer?
- Does it give the right *amount* of information — not padded, not too terse?
- Does it anticipate the obvious follow-up need without going off on a tangent?

### 2. Accuracy / Honesty
Is everything stated true, and is uncertainty represented honestly?
- Are factual claims correct and checkable?
- Does the response distinguish between what it knows confidently and what it's inferring or guessing?
- Are sources, numbers, quotes, or citations real and correctly represented (not fabricated or misattributed)?

### 3. Safety / Harmlessness
Could the response cause harm to the user or others if acted on?
- Does it avoid providing dangerous operational detail (weapons, malware, self-harm methods)?
- Does it handle sensitive topics (mental health, medical, legal, financial) with appropriate caution?
- Does it refuse appropriately — without being needlessly preachy, evasive, or refusing things that were actually fine?

### 4. Reasoning quality
Is the thinking behind the answer sound, not just the final answer?
- For multi-step problems (math, logic, code, planning), are the intermediate steps valid?
- Are there unstated assumptions that quietly change the outcome?
- Does the conclusion actually follow from the stated reasoning, or does it jump?

### 5. Tone / Communication style
Is the response written in a way appropriate to the person and situation?
- Does it match the register the user needs (casual vs. professional, brief vs. thorough)?
- Is it respectful, and does it avoid being condescending, preachy, or robotic?
- Does formatting (headers, bullets, bold) aid reading or clutter it?

### 6. Instruction-following / Constraint adherence
Did the response respect the explicit constraints in the prompt?
- Word/length limits, output format (JSON, table, code-only), persona or role instructions.
- If a constraint genuinely couldn't be met, did the response say so instead of silently ignoring it?

## Why dimensions must be scored separately before being combined

If you jump straight to one overall score, your brain will anchor on whichever dimension struck you first (usually tone, because it's the most immediately felt) and under-weight the others (usually accuracy, because it takes effort to verify). Scoring dimensions independently — even briefly — forces you to actually check the ones that don't announce themselves.

**Rule of thumb:** if you can't name which dimension a problem belongs to, you haven't identified the problem yet — you've only identified a feeling.

## A worked mini-example

> **Prompt:** "What's the boiling point of water and why does it change at altitude?"
> **Response:** "Water boils at 100°C at sea level. This is because atmospheric pressure is lower at altitude, so water actually needs to reach a higher temperature to boil at higher elevations."

Dimension check:
- **Helpfulness:** Answers both parts of the question. ✅
- **Accuracy:** The direction is reversed — boiling point *decreases* at altitude, it doesn't increase. ❌ This is a factual error, not a tone or formatting issue.
- **Safety:** Not applicable / no risk. ✅
- **Reasoning:** The causal link (pressure → boiling point) is the right *mechanism*, just applied backwards. Partial credit for structure, fail for conclusion.
- **Tone:** Clear and appropriately concise. ✅
- **Instruction-following:** Both requested parts (what + why) were addressed. ✅

**Net read:** one clean, isolated accuracy failure inside an otherwise well-constructed response — not a "bad response," a response with one specific, nameable defect. That specificity is what makes the evaluation useful to whoever fixes the underlying system.

---
**Previous:** [`01-introduction-to-ai-evaluation.md`](01-introduction-to-ai-evaluation.md) · **Next:** [`03-rubrics-and-scoring-scales.md`](03-rubrics-and-scoring-scales.md)
