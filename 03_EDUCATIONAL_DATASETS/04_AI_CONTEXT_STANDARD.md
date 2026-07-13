# SydTek Alpha School

# AI Context Dataset Standard

**Repository:** SydTek Alpha School  
**Section:** Educational Datasets  
**Version:** 1.0.0  
**Status:** Canonical Technical Standard

---

# Purpose

The AI Context Dataset Standard establishes the requirements for instructional information provided to artificial intelligence systems used within SydTek Alpha School.

AI systems should never rely solely on general foundation-model knowledge when institution-specific instructional guidance is available.

Instead, SydTek AI systems retrieve approved instructional context from version-controlled AI Context Datasets.

This Retrieval-Augmented Generation (RAG) architecture improves:

- instructional consistency;
- academic accuracy;
- competency alignment;
- transparency;
- explainability;
- institutional governance;
- accreditation readiness.

---

# Definition

An AI Context Dataset is a structured instructional knowledge repository designed specifically for artificial intelligence systems.

Unlike a learner-facing dataset, an AI Context Dataset contains information optimized for machine interpretation rather than direct student instruction.

It provides institutional guidance that helps AI systems produce responses aligned with SydTek academic standards.

---

# Guiding Principles

Every AI Context Dataset must be:

- faculty approved;
- version controlled;
- competency aligned;
- explainable;
- traceable;
- auditable;
- privacy preserving;
- regularly reviewed.

AI should retrieve institutional knowledge rather than invent instructional guidance.

---

# Relationship to Educational Datasets

Every instructional dataset may have a corresponding AI Context Dataset.

Example:

```text
Biology Dataset
        │
        ▼
AI Context Dataset
        │
        ▼
AI Tutor
```

Instructional content remains the authoritative educational resource.

AI Context Datasets provide machine-readable instructional guidance.

---

# Required Components

Each AI Context Dataset should include:

- dataset identifier;
- instructional scope;
- approved terminology;
- competency mappings;
- learning outcomes;
- prerequisite knowledge;
- common misconceptions;
- recommended explanations;
- approved examples;
- assessment guidance;
- escalation rules;
- prohibited responses;
- revision history.

---

# Instructional Scope

The scope defines exactly what the AI is expected to teach.

Example:

```text
Dataset Scope

Course:
Biology I

Unit:
Cell Division

Topics:

- Mitosis
- Meiosis
- Chromosomes
- Cell Cycle

Outside Scope:

- Advanced Genetics
- Molecular Biology
```

Clearly defining scope reduces inaccurate responses.

---

# Competency Alignment

Every AI Context Dataset maps directly to institutional competencies.

Example:

```yaml
competencies:

- BIO-101

- BIO-102

- SCI-203
```

AI tutoring recommendations should always reinforce approved competencies.

---

# Learning Outcomes

The AI Context Dataset includes the official learning outcomes associated with instructional content.

Example:

```text
After completing this dataset, learners should be able to:

• Explain mitosis.

• Compare mitosis and meiosis.

• Identify phases of cell division.

• Interpret basic cell-cycle diagrams.
```

AI responses should reinforce—not replace—learning outcomes.

---

# Approved Terminology

Datasets identify preferred terminology.

Example:

```text
Preferred Terms

Cell Division

Chromosome

Mitosis

Meiosis

Cytokinesis
```

Terminology consistency improves instructional quality across courses.

---

# Common Misconceptions

Faculty identify misconceptions frequently observed among learners.

Example:

```text
Common Misconceptions

Mitosis creates reproductive cells.

Meiosis produces identical cells.

DNA doubles after mitosis.

Chromosomes disappear permanently.
```

AI tutors proactively address common misunderstandings.

---

# Recommended Explanations

Faculty-approved explanations improve consistency.

Example:

```text
Explain mitosis using:

• sequential phases;

• chromosome movement;

• daughter cell formation;

• biological purpose.

Avoid unnecessary graduate-level terminology when tutoring introductory learners.
```

---

# Approved Examples

Examples should illustrate authentic learning.

Example:

```text
Approved Examples

Human skin repair

Plant root growth

Embryonic development

Bone marrow cell production
```

Examples should be developmentally appropriate.

---

# Assessment Guidance

AI systems should support learning without compromising assessment integrity.

Approved assessment support may include:

- study guidance;
- practice questions;
- formative feedback;
- concept clarification;
- learning strategies.

AI should never disclose:

- secure examination answers;
- restricted assessment materials;
- unpublished grading keys;
- confidential rubrics.

---

# Escalation Rules

Some learner questions require human intervention.

Examples include:

- suspected academic misconduct;
- disability accommodations;
- grading disputes;
- mental health concerns;
- harassment;
- threats of violence;
- legal questions.

The AI should recommend appropriate institutional resources rather than attempting to resolve these situations independently.

---

# Prohibited Responses

AI Context Datasets identify responses that should never be generated.

Examples include:

- inventing institutional policy;
- assigning grades;
- overriding faculty decisions;
- issuing official academic approvals;
- generating fraudulent documentation;
- bypassing competency requirements.

---

# Retrieval Architecture

Recommended workflow:

```text
Learner Question

        │

        ▼

AI Retrieves Context Dataset

        │

        ▼

Foundation Model

        │

        ▼

Faculty-Approved Response

        │

        ▼

Learner
```

This architecture reduces hallucinations and improves instructional consistency.

---

# Privacy Requirements

AI Context Datasets must not contain:

- student education records;
- personally identifiable information;
- confidential personnel information;
- restricted assessment content.

Instructional context remains separate from protected learner data.

---

# Version Control

AI Context Datasets follow Semantic Versioning.

Major revisions occur when:

- learning outcomes change;
- competencies change;
- instructional scope changes;
- approved terminology changes significantly.

Minor revisions include:

- improved explanations;
- additional examples;
- updated misconceptions.

---

# Faculty Governance

Faculty approve:

- instructional scope;
- terminology;
- explanations;
- competency mappings;
- assessment guidance.

AI Context Datasets remain academic documents under faculty governance.

---

# Quality Assurance

Quality reviews evaluate:

- instructional accuracy;
- AI response consistency;
- learner feedback;
- faculty feedback;
- competency alignment;
- accessibility;
- hallucination frequency.

Quality improvements become future dataset versions.

---

# Institutional Licensing

AI Context Datasets may be licensed separately from learner-facing instructional datasets.

Institutional licensing may include:

- AI tutoring systems;
- white-label educational platforms;
- enterprise learning systems;
- workforce education.

Licensing agreements should define:

- permitted AI models;
- update frequency;
- attribution;
- redistribution rights;
- support expectations.

---

# Relationship to the SydTek Canon

The AI Context Dataset Standard implements:

- Educational Dataset Standard;
- Metadata Standard;
- Version Control Standard;
- Competency Framework;
- AI Governance Framework.

AI systems operating within SydTek should retrieve institutional knowledge through approved AI Context Datasets.

---

# Next Educational Dataset Standard

Continue to:

```text
03_EDUCATIONAL_DATASETS/05_COMPETENCY_MAPPING.md
```