# Ephemeral Organizations — Vision

## Problem

Agent creation is becoming inexpensive. Model access, tool protocols, agent-to-agent interaction, and harnesses are progressively commoditizing the mechanics of autonomous execution.

The emerging problem is organizational:

> How can a mission cause the formation of the right temporary computational organization, with bounded resources and authority, while preserving accountability and evidence?

## Thesis

The durable abstraction may not be the individual agent. It may be the **mission-funded organization**.

```text
Mission
  │
  ├── Principal
  ├── Budget / resources
  ├── Authority
  ├── Constraints
  ├── Risk
  └── Evidence requirements
       ↓
Organization Formation
       ↓
Temporary governed organization
       ↓
Execution
       ↓
Outcome + Evidence
       ↓
Dissolution
```

An organization may contain many agents, models, humans, tools, services, or sub-organizations. Those internal implementation choices should not necessarily be exposed to consumers of the organization's capabilities.

## Why ephemeral?

Traditional organizations incur substantial formation and coordination costs. Computational organizations can potentially be assembled, changed, evaluated, and dissolved much faster.

This creates a testable economic hypothesis:

> Mission-specific ephemeral organizations can reduce the cost and time required to test organizational designs and business hypotheses before committing to permanent structures.

This hypothesis is not yet demonstrated universally and should be measured empirically.

## Strategic distinction

The project does not aim to build another agent framework or another agent-to-agent protocol.

Existing and emerging protocols can provide lower-level infrastructure. The proposed layer treats an **organization as a first-class operational entity** with:

- identity;
- accountable Principal;
- mission;
- capabilities;
- bounded authority;
- resources;
- contracts;
- evidence;
- lifecycle and expiry.

## Potential market layers

The open specification itself is not assumed to be the commercial product. Potential implementation markets include:

- Mission-to-Organization runtime;
- enterprise organization control plane;
- organization identity and registry;
- authority/policy infrastructure;
- evidence and conformance tooling;
- hosted execution;
- organization-to-organization service exchange;
- future mission marketplaces.

A plausible open-core structure is:

```text
Open specification
      ↓
Reference implementation
      ↓
Commercial runtime
      ↓
Enterprise control plane
      ↓
Registry / trust infrastructure
      ↓
Mission marketplace (future)
```

## Economic primitive

Model tokens, compute, monetary budgets, API quotas, and human attention can all be treated as bounded Mission resources. Future organizations may dynamically allocate these resources to maximize Mission outcomes.

Tokens are not assumed to be money. They are initially treated as measurable computational resources.

## Legal boundary

An Ephemeral Operational Organization is not automatically a legal person.

Operational authority and legal authority are separate. The organization acts under authority traceable to an accountable Principal. Actions such as contracting, purchasing, banking, employment, regulated decisions, or legal representation may require additional human or legal authorization outside the EORS model.

## Long-term direction

A future computational economy may evolve through layers:

```text
Models
  ↓
Agents
  ↓
Harnesses
  ↓
Agent networks
  ↓
Organizations
  ↓
Organization networks
  ↓
Mission / capability markets
```

The project focuses first on the organization layer. It should interoperate with lower-level protocols rather than unnecessarily replacing them.

## Research discipline

The project must distinguish:

```text
vision
≠ hypothesis
≠ implemented capability
≠ measured result
≠ standard
```

Claims about cost reduction, market size, legal treatment, safety, interoperability, or economic impact require evidence appropriate to the claim.
