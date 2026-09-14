# Ephemeral Organization Runtime Specification (EORS) v0.1

**Status:** Experimental / pre-standardization  
**Track:** Ephemeral computational organizations  
**Relationship to EGASE:** Complementary. EGASE governs evidence and authoritative claims in agentic engineering; EORS defines how a mission may instantiate, operate, and terminate a governed computational organization.

## 1. Abstract

EORS defines a minimal model for creating temporary computational organizations around explicit missions.

An Ephemeral Operational Organization (EOO) is a bounded computational organization composed of agents, models, tools, services, humans, or other capabilities assembled to pursue a mission under explicitly delegated authority. An EOO is not, by virtue of this specification, a legal person.

The core thesis is:

> A mission may instantiate a temporary computational organization whose authority is explicitly delegated, bounded, attributable, auditable, revocable, and terminable.

EORS is intentionally model-, harness-, orchestration-, protocol-, vendor-, and sector-neutral.

## 2. Motivation

Agent frameworks increasingly make it inexpensive to create autonomous workers. The harder problem is no longer only how to create an agent, but how to form a temporary organization that can coordinate multiple capabilities while preserving responsibility, authority boundaries, evidence, cost controls, and termination semantics.

EORS treats the organization, rather than the individual agent, as a first-class operational entity.

The intended transformation is:

```text
Mission
  + Principal
  + Resources
  + Constraints
  + Authority
        ↓
Organization Formation
        ↓
Governed Execution
        ↓
Evidence + Outcome
        ↓
Expiry / Dissolution
```

## 3. Scope

EORS specifies:

- the minimum information required to define a mission;
- the identity and lifecycle of an EOO;
- the relationship between an EOO and its accountable principal;
- capability assignment;
- delegated and bounded authority;
- resource and budget constraints;
- execution evidence and provenance requirements;
- expiry, revocation, and dissolution semantics;
- interoperability boundaries with agent/tool protocols.

EORS does not specify:

- a particular LLM or foundation model;
- a particular agent framework or harness;
- a particular workflow engine;
- a new legal entity type;
- cryptocurrency or a mandatory payment mechanism;
- a universal agent addressing scheme;
- replacement for MCP, A2A, HTTP, OAuth, PKI, or existing identity/security protocols.

## 4. Normative language

The key words **MUST**, **MUST NOT**, **REQUIRED**, **SHOULD**, **SHOULD NOT**, and **MAY** indicate requirements for implementations claiming EORS conformance. This experimental specification does not claim IETF, ISO, IEEE, NIST, W3C, or other accredited-standard status.

## 5. Core primitives

### 5.1 Mission

A **Mission** is the bounded objective that justifies formation of an EOO.

A Mission MUST define:

- a stable identifier;
- an objective;
- success or termination criteria;
- applicable constraints;
- an accountable Principal;
- an authority envelope;
- an expiry condition.

A Mission SHOULD define budgets, evidence requirements, risk classification, and expected outputs.

### 5.2 Principal

A **Principal** is the identifiable human or legal entity from which operational authority ultimately derives.

An EOO MUST have at least one accountable Principal.

An EOO MUST NOT be treated as possessing independent legal authority merely because it can act autonomously.

### 5.3 Organization

An **Ephemeral Operational Organization (EOO)** is a temporary computational structure instantiated to pursue a Mission.

An EOO MUST have:

- a unique organization identifier;
- a Mission;
- an accountable Principal;
- a defined capability set;
- an authority envelope;
- a lifecycle state;
- an expiry condition;
- an evidence boundary.

An EOO MAY contain agents, humans, services, models, tools, workflows, sub-organizations, or combinations thereof.

### 5.4 Identity

**Organization Identity** is the stable operational identity by which an EOO is referenced during and, where required for audit, after its lifetime.

Identity MUST remain attributable after operational dissolution for at least the evidence-retention period required by the Mission or Principal.

EORS v0.1 does not reserve a URI scheme. Implementations MAY use internal identifiers such as:

```text
misyra:org:9421
misyra:org:9421:service:market-research
```

Future work MAY evaluate interoperable organization-level addressing after compatibility analysis with existing URI, agent discovery, A2A, and identity standards.

### 5.5 Capability

A **Capability** describes an operation or outcome an organization member or service can provide.

Capability is distinct from Authority:

```text
Capability = can perform X
Authority  = is permitted to perform X in this Mission
```

Possession of a Capability MUST NOT imply permission to exercise it.

### 5.6 Authority

**Authority** is an explicit delegation permitting an actor to exercise a Capability within defined boundaries.

Authority MUST be:

- attributable to a Principal or authorized delegation chain;
- scoped;
- time-bounded or revocable;
- evaluable before material action;
- auditable when exercised.

Implementations SHOULD apply least privilege and fail closed when required authority cannot be demonstrated.

Operational Authority and Legal Authority MUST be treated as distinct concepts.

### 5.7 Resource

A **Resource** is a bounded consumable available to a Mission or EOO, including compute, model tokens, monetary budget, time, API quotas, storage, human attention, or external services.

Resource allocation MAY be dynamic, but MUST remain within Mission and Principal constraints unless an authorized amendment is recorded.

### 5.8 Contract

A **Contract** defines obligations at an organizational boundary. It MAY describe service expectations, evidence requirements, budget, deadlines, allowed interactions, acceptance criteria, or settlement terms.

EORS contracts are operational artifacts and MUST NOT be assumed to constitute legally enforceable contracts unless the relevant legal requirements are independently satisfied.

### 5.9 Evidence

**Evidence** is attributable information supporting claims about execution, decisions, outputs, authority use, resource use, or acceptance.

Evidence SHOULD distinguish:

```text
hypothesis
≠ action
≠ observation
≠ evidence
≠ supported claim
≠ acceptance
```

Where EGASE is used, EORS evidence SHOULD integrate with the Agentic Engineering Execution Ledger, OCM, EAR, or other applicable evidence mechanisms rather than duplicating them.

### 5.10 Expiry

**Expiry** is the condition after which an EOO may no longer exercise operational authority.

Expiry MAY be based on time, Mission completion, budget exhaustion, Principal revocation, policy violation, risk threshold, or another deterministic condition.

Expiry MUST trigger revocation or invalidation of temporary authority.

## 6. Lifecycle

An EOO lifecycle consists of at least:

```text
DEFINED
   ↓
FORMING
   ↓
ACTIVE
   ↓
COMPLETING | REVOKED | EXPIRED | FAILED
   ↓
DISSOLVED
```

### 6.1 Defined

Mission, Principal, constraints, and initial authority are established.

### 6.2 Forming

Required capabilities are resolved. Agents, humans, tools, services, models, and workflows MAY be selected or instantiated.

### 6.3 Active

The EOO performs Mission work. Material actions MUST remain within the active authority envelope.

### 6.4 Completing

Outputs, evidence, resource accounting, unresolved risks, and acceptance state are finalized.

### 6.5 Revoked / Expired / Failed

Further authority exercise MUST cease except for explicitly authorized containment, cleanup, evidence preservation, or recovery actions.

### 6.6 Dissolved

Temporary execution authority MUST be removed. Required evidence, provenance, identity records, and accountability links MUST survive according to retention policy.

## 7. Organization formation

An implementation MAY use a compiler, planner, rules engine, human design process, or hybrid mechanism to form an EOO.

A conceptual compiler is:

```text
Organization = compile(
    Mission,
    Principal,
    AvailableCapabilities,
    Policies,
    Resources,
    Constraints,
    Risk
)
```

The compiler output SHOULD be inspectable before activation for Missions whose risk policy requires human or independent approval.

Formation MAY reuse existing agents or capabilities and MAY instantiate ephemeral ones.

## 8. Authority invariants

An EORS-conformant runtime MUST preserve these invariants:

1. **No orphan authority.** Every material authority grant traces to an accountable Principal or authorized delegation chain.
2. **Capability is not authority.** Technical ability alone never grants permission.
3. **No authority after expiry.** Expired or dissolved organizations cannot continue exercising temporary Mission authority.
4. **Bounded delegation.** A delegate cannot grant authority beyond the authority it possesses.
5. **Attributable material action.** Material actions are attributable to an organization identity and acting capability/actor.
6. **Revocability.** Temporary authority can be withdrawn according to policy.
7. **Evidence survival.** Dissolution does not erase evidence required for accountability.
8. **Fail-closed ambiguity.** Where policy requires authority and it cannot be established, the material action is denied.

## 9. Evidence-bearing execution

A completed Mission SHOULD be capable of producing an evidence package containing, proportionally to risk:

- Mission identifier;
- organization identifier;
- Principal reference;
- organization topology/version;
- authority grants exercised;
- material actions;
- resources consumed;
- supported claims;
- evidence references;
- unresolved risks;
- review/acceptance state;
- terminal lifecycle state.

The objective is not maximal logging. Evidence MUST remain proportional to the risk and significance of the claims or actions being governed.

## 10. Interoperability model

EORS is designed to sit above lower-level model, harness, agent, and tool protocols.

A non-normative conceptual stack is:

```text
Mission / Economic Layer
        ↓
Ephemeral Organization Layer   ← EORS
        ↓
Agent Interaction / Discovery  ← e.g. A2A, agent discovery mechanisms
        ↓
Harness / Runtime
        ↓
Tool & Data Access             ← e.g. MCP, APIs
        ↓
Models / Compute
```

An EOO MAY expose services through existing HTTP, A2A, RPC, messaging, or other protocols. EORS v0.1 deliberately avoids defining a competing transport protocol.

## 11. Security and trust model

Implementations SHOULD consider at least:

- Principal impersonation;
- forged organization identity;
- authority escalation;
- delegation-chain manipulation;
- agent or tool substitution;
- evidence tampering;
- resource exhaustion;
- hidden persistence after expiry;
- unauthorized sub-organization creation;
- confused-deputy behavior;
- malicious or compromised external organizations;
- model/harness compromise;
- replay of expired authority.

A future version SHOULD define a formal threat model and conformance tests for the authority invariants.

## 12. Economic model

EORS does not require an economic mechanism. However, an implementation MAY associate a Mission with budgets denominated in currency, compute, tokens, credits, quotas, or other resource units.

An EOO MAY dynamically allocate resources among capabilities when permitted by Mission policy.

Future work MAY explore machine-to-machine service procurement and settlement, but EORS v0.1 does not define tokens as currency or prescribe blockchain/cryptocurrency mechanisms.

## 13. Example

```yaml
mission:
  id: mission:market-validation:001
  objective: "Assess whether a proposed service merits a controlled market test"
  principal: principal:example-corp
  expires_at: "2026-09-17T00:00:00Z"
  constraints:
    external_contact: false
    purchasing: false
  resources:
    model_tokens: 50000000
    monetary_budget_usd: 500

organization:
  id: misyra:org:9421
  ephemeral: true
  capabilities:
    - market_research
    - evidence_verification
    - financial_analysis
    - independent_review
  authority:
    research: autonomous
    external_contact: prohibited
    purchasing: prohibited
    contract_signature: prohibited
  evidence:
    provenance_required: true
    independent_review_required: true
```

This example does not imply that `misyra` is the final product name or that the identifier syntax is standardized.

## 14. Relationship to EGASE

EGASE and EORS address different layers:

```text
EORS  → What organization exists for this Mission, under whose authority, with what lifecycle?
EGASE → What evidence supports authoritative engineering claims and acceptance?
```

They MAY be implemented independently. When used together, EORS provides organization/authority context and EGASE provides evidence-governance mechanisms for relevant engineering work.

## 15. Conformance direction

EORS v0.1 is not yet mature enough for formal certification.

Future conformance work SHOULD prioritize machine-testable invariants rather than documentation volume. Candidate checks include:

- organization has an accountable Principal;
- every active authority grant has scope and expiry/revocation semantics;
- no action succeeds using expired authority;
- dissolution revokes temporary credentials/grants;
- required evidence survives dissolution;
- delegation never exceeds parent authority.

## 16. Research questions

Open questions include:

- Can Mission-to-Organization compilation outperform manually configured agent teams in cost, speed, quality, or adaptability?
- What is the minimum useful organization identity model?
- Which actions require a legal Principal versus only an operational Principal?
- Can authority be portable across runtimes without creating escalation paths?
- How should ephemeral organizations discover and trust one another?
- When does organization-level addressing add value beyond agent-level discovery?
- What evidence is sufficient to make an autonomous organization commercially trustworthy?
- How should cognitive/compute budgets be allocated across an organization?
- Which organizational structures emerge when formation is optimized for Mission outcomes?

## 17. Pre-standardization posture

EORS is an experimental specification intended to support implementation, falsification, interoperability experiments, and independent critique.

The path to any external standards proposal SHOULD be evidence-led:

```text
Internal specification
        ↓
Reference implementation
        ↓
Independent implementation / interoperability
        ↓
Conformance tests
        ↓
Public technical paper
        ↓
Community review
        ↓
Appropriate standards venue, if justified
```

The project MUST avoid claiming novelty, universality, legal recognition, or formal standard status without evidence.
