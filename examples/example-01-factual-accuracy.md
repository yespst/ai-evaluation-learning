# Example 01 · Factual Accuracy Evaluation

## Prompt
> "Can you explain why the sky is blue, and also tell me roughly how far the Moon is from Earth?"

## Response being evaluated
> "The sky appears blue because of a phenomenon called Rayleigh scattering. Sunlight contains all colors, but as it passes through the atmosphere, shorter wavelengths (blue and violet) scatter more strongly than longer wavelengths (red and orange) because they interact more with the small molecules in the air. Our eyes are more sensitive to blue than violet, so we perceive the sky as blue rather than violet.
>
> As for the Moon, it's approximately 1.2 million kilometers from Earth on average."

---

## Dimension-by-dimension evaluation

### Accuracy — ❌ Fail on one specific claim
- The Rayleigh scattering explanation is correct: shorter wavelengths do scatter more, and the eye-sensitivity point is a genuinely good, often-omitted detail that adds real value.
- The Moon distance is wrong. The actual average Earth–Moon distance is approximately **384,400 km**, not 1.2 million km — off by roughly a factor of 3. This isn't a rounding issue; it's a factual error, and one a user might reasonably act on (e.g., in a school assignment or general knowledge context).

**Evidence:** "approximately 1.2 million kilometers from Earth on average" — checkable against any standard astronomical reference; incorrect by a large margin.

### Helpfulness — ✅ Strong
Both parts of the two-part question are addressed directly, at an appropriate depth for a general-knowledge question — not overly technical, not superficial.

### Reasoning quality — ✅ Strong (for the scattering explanation)
The causal chain (wavelength → scattering strength → perceived color, plus the eye-sensitivity nuance) is logically sound and correctly sequenced.

### Tone / Formatting — ✅ Appropriate
Plain, conversational prose matching a conversational question. No unnecessary headers or bullets for what is fundamentally a two-part factual question.

### Instruction-following — ✅ Both requested parts answered

---

## Overall verdict

**Score: 3 / 5 (Adequate, with a clear, specific error)**

This is a strong response with one identifiable, non-trivial factual error. The evaluation should **not** be "this response is bad" — it should isolate the failure precisely: the scattering explanation is accurate and well-reasoned; the Moon-distance figure is wrong by roughly 3x. A response with a correct scattering explanation and a correct distance figure would score a 4–5; the specific error caps this one at a 3, because a user relying on the numeric fact would be meaningfully misled.

## What this example teaches

- A response can be well-written, well-reasoned, and *mostly* correct while still containing a specific, gradable factual error — good evaluation names exactly which claim is wrong rather than issuing a vague "some inaccuracies" note.
- Fluency (this response reads confidently and clearly) is not evidence of correctness — the numeric claim needed independent verification, not just a "does this sound right" check.
