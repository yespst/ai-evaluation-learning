# AI Evaluation Learning

A structured collection of AI evaluation practices, response analysis examples, quality guidelines, and learning notes about evaluating AI-generated outputs — written for anyone learning to become a rigorous, consistent AI evaluator.

This repository is meant to work as a **self-paced curriculum**. If you read it in order, you go from "what does an AI evaluator actually do" to "how do I score a real response against a rubric without letting my own bias creep in."

---

## Why this repository exists

As AI systems get deployed more widely, the people who evaluate their outputs — for accuracy, safety, helpfulness, tone, and policy compliance — have an outsized influence on the quality of the final product. Good evaluation is a skill, not an instinct. It has to be learned deliberately, the same way proofreading, QA testing, or auditing is learned.

This repo collects that skill into one place: the mental models, the failure patterns, the scoring frameworks, and worked examples that make evaluation consistent and defensible instead of a matter of gut feeling.

---

## Who this is for

- People starting out as **AI response evaluators / raters** (e.g., RLHF annotators, red-teamers, quality reviewers).
- QA / quality-assurance professionals moving from a traditional industry (manufacturing, software, etc.) into **AI evaluation** roles.
- Prompt engineers and product teams who need to **self-review** model outputs before shipping.
- Anyone curious about how "is this AI response good?" gets turned into a defensible, repeatable answer.

---

## Repository structure

```
ai-evaluation-learning/
├── README.md                     ← you are here
├── docs/                         ← core concepts, read in order
│   ├── 01-introduction-to-ai-evaluation.md
│   ├── 02-evaluation-dimensions.md
│   ├── 03-rubrics-and-scoring-scales.md
│   ├── 04-common-failure-modes.md
│   ├── 05-bias-and-consistency.md
│   └── 06-comparative-evaluation-a-b-ranking.md
├── guidelines/                   ← practical standards to apply on the job
│   ├── helpfulness-guidelines.md
│   ├── harmlessness-safety-guidelines.md
│   ├── honesty-accuracy-guidelines.md
│   ├── tone-and-formatting-guidelines.md
│   └── edge-case-handling-guidelines.md
├── examples/                     ← worked, annotated response analyses
│   ├── example-01-factual-accuracy.md
│   ├── example-02-harmful-request-refusal.md
│   ├── example-03-code-generation-review.md
│   ├── example-04-tone-and-empathy.md
│   └── example-05-comparative-ranking.md
├── templates/                    ← reusable templates for real evaluation work
│   ├── single-response-scorecard.md
│   ├── pairwise-comparison-template.md
│   └── error-taxonomy-checklist.md
├── notes/                        ← ongoing learning log
│   └── learning-notes.md
├── GLOSSARY.md
├── CONTRIBUTING.md
└── LICENSE
```

---

## How to use this repository

1. **Start with `docs/`** in numeric order — it builds the vocabulary and mental models you'll need everywhere else.
2. **Read `guidelines/`** as a reference, not a novel — these are the standards you'll apply directly when scoring real responses.
3. **Study `examples/`** closely. Each one shows a real-style prompt/response pair, a full evaluation, and the reasoning behind the score — not just the final verdict.
4. **Use `templates/`** the next time you actually evaluate something. Copy the template, fill it in, done.
5. **Keep your own `notes/learning-notes.md`** updated as you go — the act of writing down what confused you is most of the learning.

---

## Core principle this repo teaches

> **A good evaluation is one a stranger could reproduce.**

If two trained evaluators look at the same response and reach very different scores, the rubric — or the evaluator's understanding of it — has failed, not the response. Everything in this repository is built around closing that gap: clearer criteria, named failure modes, calibration exercises, and worked examples that show the reasoning, not just the score.

---

## License

Released under the [MIT License](LICENSE) — free to use, adapt, and share for learning or teaching purposes.
