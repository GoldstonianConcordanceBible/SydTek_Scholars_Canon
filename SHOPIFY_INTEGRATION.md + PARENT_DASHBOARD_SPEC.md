# Shopify Integration Architecture
## SydTek Scholars + SydTek University | Single-Platform K–PhD

---

## Platform Architecture

sydtekscholars.com (Shopify — Rebel theme)
├── /                     → K–PhD pipeline landing page
├── /enroll               → Enrollment application
├── /quiz                 → Placement quiz (embedded)
├── /shop                 → Curriculum bundles by stage
├── /dashboard            → Paid parent dashboard (gated)
├── /accreditation        → Live accreditation status page
├── /university           → SydTek University pathway info
└── /account              → Login + account management


---

## K–PhD Pipeline Page (/)

The homepage serves as the full pipeline visibility page. Parents see:
1. Every stage from K–5 through PhD
2. Credentials earned at each stage
3. Transfer credit values
4. No-lock-in policy
5. Accreditation status (live badge)
6. CTA: Take placement quiz / Enroll now

**Shopify implementation:** Custom section using Liquid templating. Pipeline stages rendered as metafield-driven content blocks — updateable without code changes.

---

## Placement Quiz Integration

### Recommended Platform: Typeform or Shopify native (Quiz Kit app)

**Quiz flow:**
1. Child's current grade level
2. Prior school type (public / private / homeschool / none)
3. Learning goals (diploma / credits / microcredentials / full pipeline)
4. Theological background (none / basic / intermediate / advanced GCB)
5. Parent involvement level preference
6. State of residence (triggers compliance notice)

**Output:**
- Recommended entry stage
- Recommended curriculum track
- State compliance notice for home state
- Direct CTA to enroll at recommended level

**Shopify connection:**
- Quiz completion triggers Shopify customer tag assignment
- Tag determines which products appear in /shop
- Tag populates dashboard entry stage on first login

---

## Curriculum Bundles (Shopify Products)

| Product | Stage | Contents | Price Tier |
|---|---|---|---|
| Mirror Bundle | K–5 | Full year curriculum access, reflection guides, progress logs | Mirror tier |
| Water Bundle | 6–8 | Full year curriculum access, writing assignments, assessment tools | Water tier |
| Fire Bundle | 9–12 | Full year + dual enrollment modules + diploma track | Fire tier |
| University Prep Add-On | 9–12 | 12-credit microcredential package | Premium |
| Microcredential — Theology 101 | 9–12 | Single course, 3 credits | À la carte |
| Microcredential — AI Foundations | 9–12 | Single course, 3 credits | À la carte |
| K–PhD Full Pipeline | All | All stages unlocked | Institutional |

---

## Parent Dashboard (Gated — Paid Members)

**Access:** Purchase of any curriculum bundle unlocks dashboard access.
**URL:** `sydtekscholars.com/dashboard`
**Authentication:** Shopify customer account login

**Dashboard sections:**
1. Student pipeline position (visual K–PhD tracker)
2. Current stage curriculum access
3. Progress logs (parent-updated)
4. Microcredential tracker
5. Accreditation status (live — pulled from GitHub repo)
6. Enrollment confirmation download
7. State compliance reference card
8. Placement quiz results
9. University pathway preview
10. Transfer credit tracker

**Auto-update mechanism:**
- Accreditation status badge updates from GitHub repo README status table
- Progress logs auto-timestamp on parent input
- Microcredential unlocks trigger on course completion confirmation

---

## Quiz → Shopify → Dashboard Flow

Parent lands on sydtekscholars.com
↓
Takes placement quiz
↓
Quiz assigns Shopify customer tag (stage + state)
↓
Parent shown recommended bundle
↓
Parent purchases bundle
↓
Dashboard unlocks with pre-populated:
- Student stage
- State compliance card
- Curriculum access for stage
- K–PhD pipeline position
↓
Parent can see entire K–PhD path from current position
↓
Child progresses → parent marks milestones → dashboard updates
↓
Microcredentials unlock → credits accrue toward SydTek University


---

## SydTek University Connection

The Shopify site serves both SydTek Scholars (K–12) and SydTek University (higher ed) as a unified K–PhD platform:

| Section | Entity | Purpose |
|---|---|---|
| K–12 curriculum products | SydTek Scholars | K–12 enrollment and instruction |
| University preview pages | SydTek University | Pathway visibility for parents |
| Dual enrollment modules | Both | Bridge products — purchased through Scholars, credited to University |
| Transfer credit tracker | Both | Shows accumulated credits toward university degree |

**Important:** Legal entity separation is maintained. SydTek Scholars LLC and SydTek University are separate entities. The Shopify platform is the shared front-end. All revenue attributed correctly per product type.

---

*Document version: 1.0 | Last updated: 2026*

# Parent Dashboard Technical Specification
## SydTek Scholars | Paid Member Feature

---

## Overview

The SydTek Scholars Parent Dashboard is a paid-member feature accessible via `sydtekscholars.com/dashboard`. It provides real-time visibility into a child's K–PhD pathway, accreditation status, credential progress, and compliance documentation.

---

## Access Control

| Tier | Access Level | Unlock Trigger |
|---|---|---|
| Free visitor | Pipeline page only (read-only) | None |
| Enrolled (Mirror) | K–5 dashboard | Mirror bundle purchase |
| Enrolled (Water) | 6–8 dashboard | Water bundle purchase |
| Enrolled (Fire) | 9–12 dashboard | Fire bundle purchase |
| University Track | Full K–PhD dashboard | University prep purchase |
| K–PhD Full | All sections unlocked | Full pipeline purchase |

---

## Dashboard Sections

### 1. Student Profile
- Student name (editable)
- Current stage (editable — parent-updated)
- Enrollment date
- Student ID
- Home state (auto-populated from quiz)

### 2. K–PhD Pipeline Tracker
- Visual pipeline from K–5 through PhD
- Current position highlighted
- Completed stages marked
- Future stages visible (pathway transparency)
- Microcredentials earned displayed per stage

### 3. Curriculum Access
- Current stage curriculum links
- Video playlist access
- Reflection prompt downloads
- Assignment templates
- Assessment rubrics

### 4. Progress Log
- Parent-updated milestone check-ins
- Auto-timestamped entries
- Exportable as PDF for state compliance documentation
- Cumulative seat time calculator

### 5. Microcredential Tracker
- Credits earned (current stage)
- Credits pending
- Credits projected to SydTek University
- No-lock-in credit summary

### 6. Accreditation Status
- Live Cognia track progress (9-step visual)
- Current phase badge
- Estimated accreditation date range
- What accreditation means for the student's diploma

### 7. Compliance Documents
- Enrollment confirmation letter (PDF download)
- State compliance reference card (auto-populated by home state)
- Withdrawal letter template (if applicable)
- Curriculum overview (for districts requiring documentation)

### 8. University Pathway Preview
- SydTek University program options
- Transfer credit projection based on current stage
- Application timeline (when eligible)
- Dual enrollment module availability

---

## Auto-Update Mechanisms

| Data Point | Update Source | Frequency |
|---|---|---|
| Accreditation status | GitHub repo README | On commit / daily sync |
| Progress log entries | Parent input | Real-time |
| Microcredential unlocks | Course completion confirmation | On parent submit |
| Transfer credit tally | Microcredential tracker | Calculated dynamically |
| State compliance card | Quiz tag / account settings | On state change |
| Enrollment confirmation | Purchase confirmation | Immediate |

---

## React Component Reference

The parent dashboard UI is implemented as a React component (`SydTekScholarsDashboard.jsx`) deployable via:
- Shopify custom storefront (Hydrogen / Headless)
- Embedded via Shopify theme app extension
- Standalone hosted at subdomain: `dashboard.sydtekscholars.com`

Source file: `SydTekScholarsDashboard.jsx` (repo root)

---

*Document version: 1.0 | Last updated: 2026*

# Seat Time Model
## SydTek Scholars Academy | Instructional Hours Documentation

---

## Per-Course Model

| Component | Count | Duration | Total |
|---|---|---|---|
| Video lessons | 20 | 10 min each | 200 minutes |
| Reflection per lesson | 20 | 5 min each | 100 minutes |
| Written assignment | 1 per unit (4 units) | 15 min each | 60 minutes |
| End-of-unit assessment | 4 | 20 min each | 80 minutes |
| **Total per course** | | | **~440 minutes (~7.3 hours)** |

---

## Per-Year Model

| Grade Band | Courses/Year | Hours/Course | Annual Hours |
|---|---|---|---|
| K–5 | 8 | ~5 hrs | ~40 hours |
| 6–8 | 10 | ~6 hrs | ~60 hours |
| 9–12 | 12 | ~7 hrs | ~84 hours |

> Note: These are minimum documented instructional hours. Actual engagement typically exceeds these figures due to supplemental reading, parent-led discussion, and project work.

---

## Cognia Seat Time Alignment

Cognia does not mandate a specific seat time hour count for nontraditional online schools. Instead, Cognia evaluates:
1. Whether the instructional model is documented
2. Whether seat time is consistently tracked
3. Whether student achievement evidence exists

SydTek Scholars satisfies all three:
1. This document + `CURRICULUM_FRAMEWORK.md` provide full documentation
2. Parent dashboard progress logs + YouTube watch history provide tracking
3. Reflection assignments, written responses, and assessment records provide achievement evidence

---

## Evidence Sources

| Evidence Type | Source | Public? |
|---|---|---|
| Video delivery | YouTube playlist views + timestamps | Public |
| Course structure | GitHub repository (this repo) | Public |
| Student engagement | Reflection assignments (parent-held) | Private |
| Assessment records | Student records system | Private (FERPA) |
| Progress logs | Parent dashboard | Private (member) |

---

*Document version: 2.0 | Last updated: 2026 | Replaces v1.0*
