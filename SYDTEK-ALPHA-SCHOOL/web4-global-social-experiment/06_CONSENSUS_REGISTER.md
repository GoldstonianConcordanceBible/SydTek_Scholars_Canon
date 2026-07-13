Consensus Register

Repository: GFO-token
Module: web4-global-social-experiment
Status: Canonical Consensus Infrastructure
Version: 1.0.0

⸻

Purpose

The Consensus Register records where structured agreement emerged during the modified multi-model Delphi process.

It answers the question:

“Which findings achieved meaningful agreement across independent reviewers?”

Consensus is treated as a methodological observation—not proof that a claim is true.

Agreement among reviewers increases confidence that an issue deserves attention, but it does not replace empirical evidence, legal verification, or independent expert review.

⸻

Core Principle

Consensus is evaluated only after:

Independent Review
        ↓
Cross-Model Review
        ↓
Evidence Comparison
        ↓
Structured Discussion
        ↓
Consensus Classification

The process preserves both agreement and disagreement.

⸻

Consensus Identifier

Every consensus finding receives an identifier.

Example

CON-000001
CON-000002
CON-000003

Identifiers are permanent.

⸻

Consensus Metadata

Each record should contain:

consensus_id:
title:
summary:
research_questions:
related_claims:
related_evidence:
delphi_rounds:
models:
consensus_level:
confidence:
verification_status:
repository_version:

⸻

Participating Reviewers

The repository should distinguish between:

Human Researcher
Claude
ChatGPT
Gemini
Grok
Perplexity
Future Reviewers

Additional reviewers may be added in later studies.

⸻

Delphi Round Mapping

Each consensus item records agreement by round.

round1:
round2:
round3:
replication:

Example

round1: substantial
round2: strong
round3: strong
replication: matched

⸻

Consensus Levels

The repository uses standardized classifications.

Full Consensus
Strong Consensus
Substantial Consensus
Partial Consensus
Weak Consensus
No Consensus

⸻

Full Consensus

Definition

Every participating reviewer independently reaches materially similar conclusions.

Typical Characteristics

* similar governance recommendation;
* similar reasoning;
* no material disagreement.

⸻

Strong Consensus

Definition

Most reviewers agree on the conclusion while differing slightly in reasoning or implementation.

⸻

Substantial Consensus

Definition

Agreement exists on major principles, although important implementation questions remain unresolved.

⸻

Partial Consensus

Definition

Agreement exists only on selected components.

⸻

Weak Consensus

Definition

Reviewers identify related issues but recommend different approaches.

⸻

No Consensus

Definition

No stable agreement exists.

The disagreement itself becomes a research finding.

⸻

Consensus Confidence

Very High
High
Moderate
Low

Confidence reflects stability across reviewers—not correctness.

⸻

Consensus Categories

Methodology
Theory
Governance
Legal
Privacy
Identity
Technical Controls
Compensation
Education
Healthcare
Theology
Implementation
Future Research

⸻

Example Record

consensus_id:
CON-000024
title:
Human authorization must remain central to AI identity systems.
questions:
RQ22
RQ55
RQ58
RQ73
claims:
CLM-000411
evidence:
EVD-000099
models:
Claude
ChatGPT
Gemini
Grok
Perplexity
consensus:
Strong
confidence:
High

⸻

Consensus Versus Evidence

Consensus should never replace evidence.

Instead:

Evidence
        ↓
Claims
        ↓
Consensus

Consensus strengthens confidence that the interpretation deserves consideration.

⸻

Consensus Versus Law

Agreement among reviewers does not establish:

* legal compliance;
* regulatory approval;
* statutory interpretation;
* professional advice;
* or enforceable governance.

Legal statements must still appear in the Legal Verification Register.

⸻

Consensus Versus Repository Policy

Consensus also differs from repository policy.

Example

Consensus:
Human authorization should remain central.
Repository Policy:
The Web4 implementation requires explicit authorization before persona activation.

Policy is an implementation decision.

Consensus is an analytical finding.

⸻

Consensus Evolution

Consensus may change.

Example

Round One
↓
Round Two
↓
Round Three
↓
Replication
↓
Repository Release

Older consensus remains archived.

⸻

Relationship to Dissent

Every consensus item should identify unresolved disagreement.

Example

related_dissent:
DIS-000008

This prevents false unanimity.

⸻

Relationship to Claims

Consensus links directly to:

Research Question
↓
Evidence
↓
Claim
↓
Consensus
↓
Publication

⸻

Relationship to Publications

Each consensus item identifies where it appears.

published_in:
PhilArchive
Book
Conference
Website
Substack

⸻

Website Retrieval

When a website user asks:

“What did the Delphi study conclude?”

The retrieval order should be:

Research Question
↓
Consensus
↓
Supporting Evidence
↓
Remaining Dissent
↓
Limitations
↓
Answer

⸻

Consensus Quality Checklist

Before recording consensus:

* independent reviews completed;
* reviewer identities documented;
* evidence mapped;
* claims identified;
* dissent preserved;
* legal issues separated;
* confidence assigned;
* repository version recorded.

⸻

Relationship to Other Registers

Consensus Register
        │
        ├── Claim Provenance Register
        ├── Evidence Register
        ├── Dissent Register
        ├── Legal Verification Register
        └── Version History

⸻

Canonical Principle

Consensus documents where structured agreement emerged.

It does not determine truth.

It does not replace evidence.

It does not replace law.

It does not replace expert review.

It provides a transparent record of where independent reviewers converged and where future researchers should continue testing the framework.

The retrieval chain remains:

Question
↓
Evidence
↓
Claim
↓
Consensus
↓
Remaining Dissent
↓
Legal Verification
↓
Repository Version
↓
Answer

This ensures that public responses preserve both confidence and uncertainty rather than presenting AI agreement as unquestionable fact.