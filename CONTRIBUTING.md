# Contributing

This repository is a learning resource, and it improves the same way evaluation skill improves — through specific, well-reasoned additions and corrections, not vague ones.

## Ways to contribute

- **Add a worked example** to `examples/` — a real or realistic prompt/response pair with a full, dimension-by-dimension evaluation and clear reasoning. This is the highest-value type of contribution.
- **Refine a guideline** in `guidelines/` — if you find a scoring anchor that's ambiguous or a criterion that's too vague to apply consistently, propose a sharper version.
- **Add a failure mode** to `docs/04-common-failure-modes.md` — if you've repeatedly encountered a failure pattern not yet named here, document it with a clear description and a way to detect it.
- **Share a learning-notes entry** — a genuine mistake you made and corrected is often more instructive than a polished example.

## Standards for new content

1. **Be specific, not vague.** "This response is bad because it's not helpful" is not useful. "This response fails the second part of a two-part question and states a numeric fact that is off by 3x" is.
2. **Show reasoning, not just verdicts.** Every example or guideline addition should make clear *why* a judgment was reached, in a way another person could check.
3. **Use real or realistic material.** Constructed examples should be plausible — avoid strawman responses that are obviously bad in every dimension at once; the most useful examples isolate a single, specific issue.
4. **Match the existing structure.** New examples should follow the format in `examples/` (prompt → response → dimension-by-dimension evaluation → verdict → what this teaches). New guidelines should include scoring anchors, not just prose description.
5. **Cross-reference.** Link to the relevant `docs/` or `guidelines/` file rather than re-explaining a concept that's already defined elsewhere.

## Style

- Markdown, one topic per file, numbered where sequence matters (`docs/`).
- Prefer tables for anything with more than three parallel comparisons.
- Keep prose direct — this is a working reference, not a marketing document.

## Submitting changes

1. Fork the repository.
2. Create a branch describing the change (`add-example-tone-evaluation`, `fix-rubric-scale-doc4`).
3. Open a pull request with a short description of what was added or changed and why.
