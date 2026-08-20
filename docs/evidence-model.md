# Evidence Model

EGASE distinguishes proposal, implementation, observation, claim, and acceptance.

## Evidence classes

- `DESIGN_ARTIFACT` — diagrams, wireframes, prototypes, candidate architecture.
- `SOURCE_EVIDENCE` — source code, configuration, migrations, contracts.
- `TEST_EVIDENCE` — unit, integration, contract, property, security, and regression tests.
- `DEPLOYMENT_EVIDENCE` — build/deploy records proving an artifact reached an environment.
- `RUNTIME_EVIDENCE` — observed execution under stated conditions.
- `OPERATIONAL_EVIDENCE` — monitoring, logs, delivery facts, SLO measurements, incident behavior.
- `HUMAN_REVIEW` — explicit human evaluation or acceptance.

## Claim rule

A claim must be no stronger than the evidence that supports it.

Examples:

- A wireframe may support `DESIGN_PROPOSED`, not `USABLE`.
- Passing source-level tests may support `TESTED_LOCALLY`, not `RUNNING_IN_PRODUCTION`.
- A deployment record may support `DEPLOYED`, not necessarily `CORRECT_FOR_ALL_USERS`.
- A human review may support the specific reviewed acceptance criterion, not unrelated runtime properties.

## Suggested states

```text
HYPOTHESIS_ONLY
IMPLEMENTED_NOT_EXECUTED
TESTED
DEPLOYED_NOT_OBSERVED
RUNTIME_OBSERVED
HUMAN_REVIEW_PENDING
ACCEPTED
REJECTED
DEFERRED
```

Projects may use different names, but should preserve the semantic distinction.

## Provenance

Evidence should identify enough provenance to reproduce or independently inspect the claim: source revision, environment, execution time when relevant, test or observation identity, and the scope being demonstrated.

## Proportionality

Evidence requirements should scale with consequence. A cosmetic change should not require the same evidence package as a destructive migration or authorization boundary.
