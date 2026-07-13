# SydTek Alpha School

# Educational Dataset Metadata Standard

**Repository:** SydTek Alpha School  
**Section:** Educational Datasets  
**Version:** 1.0.0  
**Status:** Canonical Technical Standard

---

# Purpose

Metadata is the foundation of the SydTek Educational Dataset ecosystem.

Every educational dataset must contain standardized metadata so that it can be:

- discovered;
- version controlled;
- licensed;
- assessed;
- mapped to competencies;
- interpreted by AI systems;
- reviewed by faculty;
- audited for accreditation;
- maintained over time.

Without metadata, educational datasets become difficult to govern, update, reuse, and license.

---

# Metadata Philosophy

Educational metadata is more than a title and description.

Metadata connects instructional content to:

- institutional learning outcomes;
- competencies;
- assessments;
- academic programs;
- faculty governance;
- AI tutoring;
- accreditation evidence;
- institutional analytics.

Metadata transforms instructional content into reusable educational infrastructure.

---

# Metadata Categories

Every dataset contains metadata organized into eight categories.

```text
Dataset Metadata

├── Identification
├── Academic Information
├── Competency Information
├── Instructional Information
├── Technical Information
├── AI Information
├── Governance Information
└── Licensing Information
```

---

# Identification Metadata

Required fields include:

| Field | Required |
|--------|----------|
| Dataset Identifier | Yes |
| Dataset Title | Yes |
| Version | Yes |
| Status | Yes |
| Repository Location | Yes |
| Creation Date | Yes |
| Last Updated | Yes |
| Dataset Owner | Yes |

Example:

```yaml
dataset_id: SYD-HS-BIO-U02-M03
title: Cell Division
version: 1.0.0
status: Approved
owner: School of Science
created: 2026-07-12
updated: 2026-07-12
```

---

# Academic Metadata

Every dataset records:

- educational level;
- grade;
- subject;
- course;
- academic department;
- academic program;
- instructional sequence;
- credit equivalency where applicable.

Example:

```yaml
level: High School
grade: 10
subject: Biology
course: Biology I
department: Natural Sciences
```

---

# Learning Outcome Metadata

Every dataset identifies:

- learning outcome identifier;
- learning outcome statement;
- mastery expectation;
- assessment alignment.

Example:

```yaml
learning_outcomes:

- LO-101
- LO-102
- LO-103
```

---

# Competency Metadata

Each dataset maps directly to institutional competencies.

Metadata should include:

- competency identifier;
- competency title;
- competency level;
- prerequisite competencies;
- related competencies.

Example:

```yaml
competencies:

- COMP-BIO-01
- COMP-BIO-02
```

---

# Instructional Metadata

Instructional metadata documents:

- estimated completion time;
- instructional format;
- laboratory requirements;
- project requirements;
- discussion requirements;
- instructional resources.

Example:

```yaml
instruction_time: 5 hours
lab_required: true
project_required: false
```

---

# Assessment Metadata

Assessment metadata includes:

- assessment type;
- mastery threshold;
- rubric identifier;
- reassessment policy;
- faculty verification requirement.

Example:

```yaml
assessment:

type: Laboratory

mastery: 80%

faculty_review: true
```

---

# Accessibility Metadata

Accessibility fields include:

- captions available;
- transcript available;
- screen-reader compatibility;
- accessible documents;
- language availability;
- accessibility review date.

Example:

```yaml
accessibility:

captions: true

transcript: true

screen_reader: true
```

---

# AI Metadata

AI-specific metadata documents how the dataset interacts with AI systems.

Fields include:

- AI compatible;
- approved AI models;
- AI tutoring enabled;
- AI prompt template;
- AI context dataset reference;
- hallucination safeguards.

Example:

```yaml
ai_support:

enabled: true

context_dataset: AI-BIO-101

approved_models:

- GPT

- Claude

- Gemini
```

---

# Version Metadata

Every dataset records:

- version number;
- version history;
- previous version;
- publication date;
- approval date;
- effective date.

Example:

```yaml
version:

current: 1.2.0

previous: 1.1.0

approved: 2026-07-12
```

---

# Faculty Metadata

Faculty metadata identifies:

- academic owner;
- content author;
- reviewer;
- approver;
- subject-matter expert;
- instructional designer.

This improves accountability and audit readiness.

---

# Licensing Metadata

Every dataset documents:

- copyright owner;
- license type;
- redistribution rights;
- modification rights;
- commercial restrictions;
- institutional licensing status.

Example:

```yaml
license:

owner: SydTek Alpha School

type: Institutional

commercial_use: Restricted
```

---

# Analytics Metadata

Datasets may include fields supporting institutional analytics.

Examples:

- learner completion rate;
- average assessment score;
- competency attainment rate;
- AI utilization;
- faculty review frequency.

Analytics support continuous improvement while remaining separate from personally identifiable student information.

---

# Accreditation Metadata

Datasets should map to accreditation evidence where applicable.

Metadata may identify:

- institutional learning outcomes;
- program outcomes;
- accreditation standards;
- assessment evidence;
- curriculum maps.

This simplifies accreditation reporting.

---

# Security Metadata

Datasets are classified according to institutional sensitivity.

Suggested levels:

- Public
- Internal
- Restricted
- Highly Restricted

Assessment answer keys should never be stored in public repositories.

---

# Required Metadata Validation

Before publication every dataset must pass validation.

Validation confirms:

- required fields completed;
- identifiers unique;
- competency mappings valid;
- version numbers correct;
- licensing complete;
- accessibility fields completed.

Datasets failing validation cannot be published.

---

# Metadata Schema Example

```yaml
dataset_id:

title:

version:

status:

owner:

academic_level:

subject:

course:

learning_outcomes:

competencies:

estimated_time:

assessment:

accessibility:

ai_support:

license:

review_date:
```

Institutions may extend the schema while preserving required fields.

---

# Metadata Governance

Metadata changes follow institutional version-control procedures.

Material metadata changes requiring approval include:

- competency mappings;
- ownership;
- licensing;
- educational level;
- assessment requirements.

Minor formatting updates may follow simplified review.

---

# Continuous Improvement

Metadata quality is evaluated using:

- completeness;
- consistency;
- discoverability;
- faculty usability;
- AI effectiveness;
- accreditation support.

Metadata standards evolve alongside institutional needs.

---

# Relationship to the SydTek Canon

The Metadata Standard implements:

- Educational Dataset Standard;
- Version Control;
- Competency Framework;
- AI Governance;
- Institutional Licensing.

Every educational dataset within SydTek should conform to this metadata standard.

---

# Next Educational Dataset Standard

Continue to:

```text
03_EDUCATIONAL_DATASETS/03_VERSION_CONTROL.md
```