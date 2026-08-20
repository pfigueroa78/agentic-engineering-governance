# EGASE v0.1 Method

EGASE is a lightweight governance layer for AI-assisted software engineering. It is intentionally not a full delivery methodology.

## Flow

```text
Human Intent + Context + Hard Constraints
                ↓
        Open Agent Reasoning
                ↓
        QSEM when needed
                ↓
        Candidate Design
                ↓
          Implementation
                ↓
        EAR / Evidence Review
                ↓
       Human or Runtime Acceptance
```

## Step 1 — Frame intent

Capture the outcome, material constraints, known authorities, and explicit non-goals. Do not convert every detail into a rule.

## Step 2 — Let the agent reason

The agent may propose architecture, workflows, patterns, alternatives, and implementation strategies. New ideas are hypotheses until promoted by evidence and authority.

## Step 3 — Use QSEM selectively

Apply QSEM when a material technical or quality choice has competing strategies whose consequences should be predicted and tested.

Do not create a QSEM document for trivial or easily reversible decisions.

## Step 4 — Implement vertically

Prefer a coherent product slice over excessive pre-implementation documentation. Preserve compatibility and approved invariants.

## Step 5 — Use EAR selectively

EAR checks experience discovery, synthesis, evidence, claims, and acceptance boundaries for changes that materially affect human interaction or experience.

EAR must not prescribe a fixed number of screens, wireframes, alternatives, or journeys.

## Step 6 — Evaluate evidence

Classify what is actually demonstrated by source inspection, tests, deployment, runtime behavior, operations, and human review.

## Step 7 — Accept proportionally

A reversible low-risk change should not require the same ceremony as a security boundary, destructive migration, financial rule, or irreversible operational decision.

## Minimum Necessary Decision

When the agent encounters uncertainty, ask whether the decision is required now to progress safely. If not, defer it with explicit scope instead of creating a new human decision gate.

## Stop condition for governance growth

If a proposed governance artifact does not materially alter a decision, reduce risk, improve evidence quality, or prevent a known failure mode, do not add it by default.
