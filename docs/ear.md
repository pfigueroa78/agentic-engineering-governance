# EAR — Experience Architecture Review

EAR governs the relationship between experience discovery, design synthesis, evidence, claims, and acceptance.

It is designed to prevent two opposite failures:

- unsupported experience claims;
- over-governance that prevents useful design exploration.

## Stages

1. **Experience discovery** — identify material human-facing concerns introduced or changed by intent, domain, or system behavior.
2. **Design synthesis** — propose a coherent experience response. Proposals may remain hypotheses.
3. **Journey/state review** — check that material states and transitions are not omitted within the designed journey.
4. **Evidence review** — classify what artifacts and runtime observations actually demonstrate.
5. **Acceptance boundary** — identify what still requires human, operational, security, or runtime validation.

## Dispositions for discovered concerns

A material concern should receive an explicit disposition such as:

- new human experience;
- existing journey sufficient;
- system-to-system only;
- no material human interaction;
- deferred by a governed dependency;
- design hypothesis pending review.

This is coverage accounting, not a requirement to create UI.

## Evidence discipline

A wireframe demonstrates a design proposal, not usability. A screenshot demonstrates rendered state, not necessarily end-to-end behavior. Source inspection demonstrates implementation intent, not runtime execution. Runtime evidence demonstrates observed behavior under stated conditions, not universal correctness.

## Reasoning preservation

EAR should audit proposals after open synthesis rather than constrain every idea before synthesis. A proposal may be `HYPOTHESIS_ONLY` while still being useful for design exploration.

## Anti-patterns

- requiring a fixed number of screens or alternatives;
- treating journey-state coverage as proof that all relevant journeys were discovered;
- using a boolean such as `discovery_complete: true` without traceable concern coverage;
- treating screenshots as human acceptance;
- requiring EAR for changes with no meaningful human-experience impact.
