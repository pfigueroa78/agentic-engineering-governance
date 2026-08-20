# Case Study 01 — Enterprise Multi-Surface Platform

> This case study preserves methodological lessons only. It intentionally omits client, organization, geography, sector, proprietary product names, private repository identifiers, and distinctive business-domain entities.

## Context

A multi-surface enterprise software platform was developed with substantial AI-agent participation across architecture, backend services, web experience, mobile compatibility, persistence, testing, and engineering governance.

The project was used to explore whether stronger evidence and change-control mechanisms could make agentic development more reliable and auditable.

## What worked

The governance approach improved:

- separation between hypotheses, evidence, and accepted claims;
- durable architecture and quality decisions;
- source/runtime provenance discipline;
- explicit authority boundaries in material domain changes;
- historical traceability of decisions;
- negative and fail-closed testing;
- separation between runtime evidence and human usability acceptance.

QSEM was useful when material architectural choices required comparing strategies and making quality predictions testable.

EAR was useful when auditing evidence for already-understood human journeys and preventing design artifacts or screenshots from being overstated as usability proof.

## What failed

The first governance design accumulated too many early constraints and negative instructions.

The workflow increasingly optimized for:

```text
avoid unsupported behavior
→ avoid unsupported hypothesis
→ minimize new interaction
→ minimize design exploration
```

Artifacts could therefore be formally correct while still incomplete from a product perspective.

### Cognitive anchoring

EAR initially concentrated on already-known journeys. Journey State Coverage could show that known journeys had state coverage while a completely new human task introduced by a domain change remained undiscovered.

### Over-governance

The process generated repeated human micro-decisions, additional artifacts, and cost that were not always proportional to the risk being controlled.

This exposed a key failure mode:

> A governance system can pass its own gates while reducing the reasoning quality of the agent it governs.

### Evidence theater risk

Adding another boolean such as `discovery_complete: true` would not solve the problem. The method needed traceable concern coverage and open synthesis rather than additional ceremony.

## Correction

The method was changed so that:

1. intent and domain changes are explored before existing journeys constrain analysis;
2. new proposals may remain `HYPOTHESIS_ONLY` without supported claims;
3. discovery coverage does not force UI or alternatives where none are needed;
4. design synthesis is distinct from evidence review;
5. governance is strongest when a proposal becomes authoritative or a material claim is made;
6. process cost itself becomes an engineering signal.

## Resulting principle

> **Govern the transition from reasoning to authority, not reasoning itself.**

## Open questions

The corrected method is not yet proven universally effective. Open questions include whether it reduces human interventions, lowers rework, preserves reasoning completeness, improves defect detection, and keeps evidence proportional to risk.

## Next validation

A second independent software project should apply the lighter approach from the start and measure delivery cost, intervention frequency, defect escape, evidence quality, and reasoning completeness. The method remains provisional until multiple independent cases exist.
