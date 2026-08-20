# Agentic Engineering Governance

**Experimental specification v0.1 for evidence-governed software engineering with AI agents.**

Agentic Engineering Governance explores a practical question: **how can software teams preserve the reasoning power of AI coding agents while keeping decisions, evidence, authority, execution provenance, and acceptance governable?**

The repository proposes an umbrella approach tentatively called **Evidence-Governed Agentic Software Engineering (EGASE)**.

## EGASE component model

Four complementary concerns form the emerging model:

- **QSEM — Quality Strategy & Experiment Model** (`v0.1 experimental`): makes quality hypotheses, candidate strategies, trade-offs, experiments, and acceptance evidence explicit without prescribing implementation.
- **EAR — Experience Architecture Review** (`v0.1 experimental`): separates experience discovery, design synthesis, evidence, supported claims, and human/runtime acceptance.
- **OCM — Operational Conformance Model** (`emerging`): captures what the software actually demonstrated at runtime under relevant operational conditions.
- **Agentic Engineering Execution Ledger** (`emerging`): preserves attributable execution provenance so evidence can be tied to the engineering execution that produced it.

The components answer different questions:

```text
QSEM    → What quality outcome do we expect, why, and how will we test it?
Ledger  → What material engineering execution actually occurred?
OCM     → What did the running software actually demonstrate?
EAR     → What claims are supported by the available evidence, and what still needs acceptance?
```

Not every project or change requires all four components. **Proportionality is a core requirement.**

## Core thesis

> Govern what an agent may **claim, change, or promote as authoritative** — not every idea it may reason about or propose.

A simplified flow is:

```text
Human Intent / Constraints
          ↓
   Open Agent Reasoning
          ↓
         QSEM
          ↓
Design / Implementation
          ↓
    ┌─────┴─────┐
    ↓           ↓
 Ledger        OCM
    └─────┬─────┘
          ↓
         EAR
 Evidence → Supported Claims
          ↓
       Acceptance
```

This repository is deliberately lightweight. It was created after observing that excessive governance can become counterproductive: a workflow can pass every gate while suppressing useful exploration and slowing the product it is supposed to protect.

## Evidence and hallucination containment

EGASE investigates whether evidence-governed engineering can reduce the **impact and propagation of unsupported AI-generated assertions**.

It does **not** claim that governance prevents a model from generating a hallucination. Instead, it aims to make unsupported assertions harder to promote into authoritative engineering state by requiring explicit separation between:

```text
hypothesis
≠ implementation
≠ observation
≠ evidence
≠ supported claim
≠ human or operational acceptance
```

This is currently a research hypothesis, not a demonstrated universal result. Future case studies should measure unsupported-claim escape rates and false-confidence failures rather than simply asserting that hallucinations decreased.

## Design goals

- Preserve agent reasoning and design exploration.
- Keep material decisions attributable and reviewable.
- Require evidence proportional to the risk of the claim.
- Separate hypothesis, implementation, observation, evidence, claim, and acceptance.
- Preserve execution provenance where it materially improves trust.
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
│   ├── ocm.md
│   ├── ledger.md
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

This is not an ISO, IEEE, NIST, or other accredited standard. QSEM and EAR have initial public specifications; OCM and Ledger are intentionally marked emerging until independent project evidence identifies their minimum useful form.

## Non-goals

EGASE is not intended to replace Scrum, Kanban, DevOps, architecture methods, ADRs, SRE, test frameworks, secure SDLC practices, or software-supply-chain provenance standards. It is a governance and evidence layer that can coexist with them.

## First anonymized case study

The first case study documents a multi-surface enterprise software platform developed with substantial AI-agent participation. It records both strengths and failure modes of evidence-heavy governance while deliberately withholding client, location, sector, product, and proprietary domain clues.

## License

Apache License 2.0. Contributions and independent implementations are welcome.
