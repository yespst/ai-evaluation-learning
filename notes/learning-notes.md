# Learning Notes

A running log of things learned, questions that came up, and corrections made while practicing AI evaluation. Keeping this updated is one of the most effective ways to actually retain evaluation skill — writing down *why* something confused you is often more useful than the resolution itself.

Suggested format for each entry:

```
## [Date] — [Short topic title]

**What I was evaluating:**

**What I got wrong / found confusing:**

**What I learned / the correction:**

**How I'll apply this next time:**
```

---

## Example entry (delete or replace once you have real ones)

## 2026-01-15 — Length bias in helpfulness scoring

**What I was evaluating:** Two responses to a simple factual question, one 3 sentences, one 3 paragraphs.

**What I got wrong / found confusing:** Initially scored the longer response higher on "helpfulness" without checking whether the extra length actually added new, relevant information.

**What I learned / the correction:** Re-read both responses specifically asking "what would be lost if this were shorter?" The longer response mostly restated the same point three different ways — no additional value, just additional words.

**How I'll apply this next time:** Before scoring helpfulness, explicitly check whether length is doing real work or just accumulating. See `guidelines/helpfulness-guidelines.md`.

---

*(Add your own entries above this line, most recent at the top or bottom — pick one convention and stay consistent.)*
