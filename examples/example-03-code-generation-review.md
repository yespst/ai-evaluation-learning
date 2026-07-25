# Example 03 · Code Generation Review

## Prompt
> "Write a Python function that takes a list of numbers and returns the average, ignoring any non-numeric values in the list."

## Response being evaluated

```python
def average_ignoring_non_numeric(values):
    numeric_values = [v for v in values if isinstance(v, (int, float))]
    return sum(numeric_values) / len(numeric_values)
```

> "This function filters out any non-numeric values using `isinstance`, then computes the average of what's left."

---

## Dimension-by-dimension evaluation

### Correctness — ⚠️ Mostly correct, one real bug
- The filtering logic is correct: `isinstance(v, (int, float))` correctly identifies numeric values and excludes strings, `None`, lists, etc.
- **Bug:** if `values` contains no numeric elements at all (empty list, or all non-numeric), `numeric_values` will be empty and `len(numeric_values)` will be `0`, causing a `ZeroDivisionError`. This is a real, likely-to-occur edge case, not an obscure one — any caller passing an empty or fully-non-numeric list will crash.
- **Secondary note:** `isinstance(v, (int, float))` will treat `True`/`False` as numeric (since `bool` is a subclass of `int` in Python), which is a subtle correctness issue depending on intent — worth flagging even though the prompt didn't specify booleans.

### Reasoning quality — ✅ Sound for the covered case
The core approach (filter, then average) is the right structure for the stated problem. The bug is a missed edge case, not a flawed overall design.

### Instruction-following — ✅ Matches the literal request
The prompt asked exactly for "average, ignoring non-numeric values" — this is delivered for the happy path.

### Communication — ⚠️ Under-explained
The one-sentence explanation doesn't mention the function's behavior on edge cases (empty input, no numeric values) at all — a stronger response would proactively flag this, since it's the kind of thing a careful engineer would call out unprompted.

---

## Overall verdict

**Score: 3 / 5 (Adequate but with a real, findable bug)**

This response would pass a quick glance-review and might even pass a shallow code review, which is exactly why it's a good calibration example: the bug only shows up when you specifically test (or reason through) the boundary condition, not when you read the code start to end. An evaluator who only checks "does this look like reasonable code" without tracing the edge cases would miss it.

### What a 5/5 response would have included
```python
def average_ignoring_non_numeric(values):
    numeric_values = [v for v in values if isinstance(v, (int, float)) and not isinstance(v, bool)]
    if not numeric_values:
        raise ValueError("No numeric values found in the input list.")
    return sum(numeric_values) / len(numeric_values)
```
Plus an explanation that explicitly calls out both the empty-input handling and the boolean edge case as deliberate choices.

## What this example teaches

- **Code evaluation requires tracing execution on edge cases, not just reading for plausibility.** The bug here is invisible on a read-through and only appears when you deliberately think through boundary inputs (empty list, all-non-numeric list).
- A correct-looking function with an untested edge case is a **specific, nameable defect** — the evaluation should identify exactly which input triggers the failure, not just say "might have edge case issues."
- Communication quality is itself gradable: a response that silently ships an edge-case risk without mentioning it is weaker than one that flags the same risk even without fully solving it.
