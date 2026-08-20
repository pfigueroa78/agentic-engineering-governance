# Agentic Engineering Governance

**Experimental specification v0.1 for evidence-governed software engineering with AI agents.**

Agentic Engineering Governance explores a practical question: **how can software teams preserve the reasoning power of AI coding agents while keeping decisions, evidence, authority, and acceptance governable?**

The repository proposes an umbrella approach tentatively called **Evidence-Governed Agentic Software Engineering (EGASE)**. Its first two public components are:

- **QSEM — Quality Strategy & Experiment Model:** makes quality hypotheses, candidate strategies, trade-offs, experiments, and acceptance evidence explicit without prescribing implementation.
- **EAR — Experience Architecture Review:** separates experience discovery, design synthesis, evidence, supported claims, and human/runtime acceptance.

## Core thesis

> Govern what an agent may **claim, change, or promote as authoritative** — not every idea it may reason about or propose.

The method distinguishes:

1. Human intent and hard constraints.
2. Open agent reasoning.
3. Implementation.
4. Evidence review.
5. Acceptance.

This repository is deliberately lightweight. It was created after observing that excessive governance can become counterproductive: a workflow can pass every gate while suppressing useful exploration and slowing the product it is supposed to protect.

## Design goals

- Preserve agent reasoning and design exploration.
- Keep material decisions attributable and reviewable.
- Require evidence proportional to the risk of the claim.
- Separate hypothesis, implementation, observation, and acceptance.
- Avoid mandatory documentation that does not change a decision.
- Make failure and over-governance visible rather than hiding them behind passing gates.
- Remain tool-, model-, sector-, and vendor-neutral.

## Privacy and case-study policy

Public case studies in this repository are intentionally anonymized. Unless explicit publication authorization exists, they must not identify or make reasonably inferable any client, organization, geographic location, regulated sector, proprietary product, private repository, internal issue/PR identifier, business-domain entity, or vendor combination that could enable triangulation.

Case studies should preserve only the methodological facts needed to reproduce or challenge the engineering conclusions.

## Repository structure

```text
.
├── docs/
│   ├── principles.md
│   ├── method.md
│   ├── qsem.md
│   ├── ear.md
│   ├── evidence-model.md
│   ├── standards-position.md
│   └── case-studies/
│       └── enterprise-multisurface-platform.md
├── schemas/
│   ├── qsem.schema.json
│   └── ear.schema.json
├── examples/
│   ├── qsem.example.yaml
│   └── ear.example.yaml
├── ROADMAP.md
├── CONTRIBUTING.md
├── CITATION.cff
└── LICENSE
```

## Status

**Experimental / pre-standardization.**

This is not an ISO, IEEE, NIST, or other accredited standard. The intent is to gather implementation evidence across multiple independent software projects before proposing stronger conformance levels or formal standardization.

## Non-goals

EGASE is not intended to replace Scrum, Kanban, DevOps, architecture methods, ADRs, SRE, test frameworks, or secure SDLC practices. It is a governance and evidence layer that can coexist with them.

## First anonymized case study

The first case study documents a multi-surface enterprise software platform developed with substantial AI-agent participation. It records both strengths and failure modes of evidence-heavy governance while deliberately withholding client, location, sector, product, and proprietary domain clues.

## License

Apache License 2.0. Contributions and independent implementations are welcome.
