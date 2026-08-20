# QSEM — Quality Strategy & Experiment Model

QSEM makes material quality reasoning explicit without prescribing implementation.

Use it when a change has competing strategies, uncertain quality consequences, or material non-functional risk.

## Core elements

A QSEM record should capture:

- the quality concern;
- candidate strategies;
- predicted trade-offs;
- relevant quality attributes;
- evidence needed to discriminate between strategies;
- selected strategy and why;
- post-change result;
- residual uncertainty.

## Example lifecycle

```text
PRE_CHANGE
  concern
  candidates
  prediction
  experiment
      ↓
implementation
      ↓
POST_CHANGE
  observed evidence
  comparison with prediction
  decision confidence
```

## Rules

- QSEM is not required for every change.
- Predictions should be falsifiable where practical.
- A selected strategy does not become correct merely because it was selected.
- Post-change evidence should compare observed results with the pre-change prediction.
- If the experiment cannot run, report `NOT_EXECUTED`; do not manufacture confidence.
- Quality attributes may be drawn from an established model, project-specific SLOs, or explicit engineering criteria.

## Anti-patterns

Do not use QSEM to create artificial alternatives when only one viable strategy exists. Do not turn speculative numerical scores into pseudo-scientific certainty. Do not force human approval of reversible implementation details merely because they appear in a QSEM record.
