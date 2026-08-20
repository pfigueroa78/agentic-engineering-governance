# OCM — Operational Conformance Model

**Status: emerging / specification pending.**

OCM is the runtime-observation component of EGASE. It addresses a question that source review and tests alone cannot answer:

> What actually happened when the software executed under relevant conditions?

OCM is intended to connect quality expectations to observed operational evidence without turning every project into a mandatory observability program.

## Role

OCM may capture evidence such as:

- runtime correctness and failure behavior;
- latency, throughput, resource use, and saturation;
- concurrency and resilience behavior;
- security-relevant runtime observations;
- dependency and provider behavior;
- operational invariants;
- environment and execution context needed to interpret observations.

## Relationship to QSEM

QSEM can state a quality hypothesis and an experiment. OCM can record what the running system actually demonstrated.

```text
QSEM hypothesis
    ↓
implementation
    ↓
runtime execution
    ↓
OCM observation
    ↓
evidence available for review
```

OCM does not decide that a business, usability, or architectural claim is true merely because a metric exists. Observation and claim remain separate.

## Proportionality

OCM should be activated according to material risk. A low-risk deterministic change may need only tests. A concurrency-sensitive or operationally critical change may need real runtime observations.

The method must not require expensive runtime evidence where it cannot materially change the acceptance decision.

## Open design questions

The v0.1 repository intentionally does not freeze an OCM schema. Independent project use should help determine:

- the minimum portable observation envelope;
- how runtime context should be fingerprinted;
- which observations are durable evidence versus transient telemetry;
- how to represent unavailable runtime environments without fabricating evidence;
- how OCM should reference QSEM experiments and EAR claims.
