# Quiz Kit Integration
## SydTek Scholars | Shopify Placement Quiz Architecture

---

## App Overview

**App:** Quiz Kit: Product Quiz Maker (Presidio)
**Shopify App Store Rating:** 4.8/5 (171 reviews)
**Install:** apps.shopify.com/quiz-kit
**Pricing:** Free plan available | Paid plans from $59/mo | $249/mo for full feature set
**Free Trial:** 7 days

Quiz Kit is the placement quiz engine for SydTek Scholars. It handles conditional logic,
Shopify customer tag assignment, Klaviyo integration, and personalized result pages —
all without custom code.

---

## Why Quiz Kit for SydTek Scholars

| Requirement | Quiz Kit Capability |
|---|---|
| Conditional logic (branch by state, grade, goal) | ✅ Logic jumps built-in |
| Shopify customer tag assignment on completion | ✅ Native tag sync |
| Klaviyo integration (segmented email flows) | ✅ Syncs as profile properties |
| Personalized result pages per student type | ✅ Custom result pages |
| Email capture at quiz completion | ✅ Built-in |
| No-code visual builder | ✅ Drag-and-drop |
| Embedded on Shopify storefront | ✅ Native embed |
| Analytics on completion rates + drop-off | ✅ Built-in dashboard |

---

## Quiz Architecture

### Quiz Title
**"Find the Right Path for Your Child"**
*SydTek Scholars Placement Quiz — 6 questions, ~2 minutes*

---

### Question Flow

**Q1: How old is your child?**
- Under 5 (pre-K)
- 5–10 (grades K–5)
- 11–13 (grades 6–8)
- 14–18 (grades 9–12)
- 18+ (university pathway)

*Logic: Routes to stage-specific follow-up. Pre-K → waitlist page. 18+ → SydTek University page.*

---

**Q2: What is your child's current school situation?**
- Enrolled in public school
- Enrolled in private school
- Currently homeschooling
- Not currently enrolled

*Logic: "Public school" triggers withdrawal letter notice in results. All paths continue.*

---

**Q3: What is your primary goal?**
- Full K–PhD pipeline (long-term institutional path)
- High school diploma + college credits
- Faith-based curriculum only (no diploma needed)
- Microcredentials and skill certificates
- University preparation

*Logic: Diploma track → Fire bundle. Faith curriculum only → Mirror or Water bundle. University prep → University Prep Add-On.*

---

**Q4: How familiar is your child with the GCB framework?**
- No prior exposure
- Basic biblical literacy
- Intermediate — familiar with OT/NT structure
- Advanced — familiar with Second Temple literature

*Logic: No exposure → full onboarding track. Advanced → accelerated track flag in customer tag.*

---

**Q5: What state do you live in?**
- Delaware
- California
- Texas
- Florida
- New York
- Georgia
- Pennsylvania
- Other (text input)

*Logic: Each state triggers a compliance notice in the results page. Georgia + Pennsylvania
+ Virginia trigger additional filing notice. Delaware → simplified compliance card.*

---

**Q6: How involved do you want to be in daily instruction?**
- Highly involved (co-teaching, daily review)
- Moderately involved (weekly check-ins)
- Minimal involvement (student self-paced)

*Logic: Informs recommended curriculum pacing in results. No routing change — metadata only.*

---

## Result Pages

### Result: Mirror Track (K–5)
**Headline:** Your child is ready for the Foundation Stage.
**Body:** Based on your answers, the Mirror tier (K–5) is the right entry point.
Your child will build biblical literacy, numeracy foundations, and introduction
to the GCB canon under the Mirror doctrine — truth, accountability, and foundation.
**CTA Button:** Enroll in Mirror Bundle → `/products/mirror-bundle`
**Secondary CTA:** View full K–PhD pipeline → `/pages/pipeline`
**State notice:** [Dynamic — populated by Q5 answer]

---

### Result: Water Track (6–8)
**Headline:** Your child is ready for the Formation Stage.
**Body:** The Water tier (6–8) matches your child's age and goals.
Formation covers Second Temple literature, world history, pre-algebra,
and critical thinking under the Water doctrine — refinement and depth.
**CTA Button:** Enroll in Water Bundle → `/products/water-bundle`
**Secondary CTA:** View full K–PhD pipeline → `/pages/pipeline`
**State notice:** [Dynamic]

---

### Result: Fire Track (9–12)
**Headline:** Your child is ready for the Fire Stage.
**Body:** The Fire tier (9–12) is your child's entry point.
This stage includes diploma track, dual enrollment microcredits toward
SydTek University, and advanced GCB curriculum.
Up to 12 university credits can be earned before graduation.
**CTA Button:** Enroll in Fire Bundle → `/products/fire-bundle`
**Secondary CTA:** View transfer credit details → `/pages/transfer-credits`
**State notice:** [Dynamic]

---

### Result: University Prep Track
**Headline:** Your child is ready for University Prep.
**Body:** Based on your goals, the University Prep Add-On is the right entry.
This package includes 12 dual-enrollment microcredits toward
SydTek University undergraduate programs.
**CTA Button:** View University Prep → `/products/university-prep`
**Secondary CTA:** View SydTek University → `/pages/university`

---

### Result: Pre-K Waitlist
**Headline:** We'll be ready when your child is.
**Body:** SydTek Scholars K–5 enrollment begins at age 5.
Join the waitlist and receive curriculum preview materials.
**CTA Button:** Join Waitlist → `/pages/waitlist`

---

## Shopify Tag Assignment (On Quiz Completion)

Quiz Kit assigns Shopify customer tags automatically on quiz submission.
Tags drive dashboard population, product display, and email flows.

| Quiz Answer | Tag Assigned |
|---|---|
| Ages 5–10 | `stage:mirror` |
| Ages 11–13 | `stage:water` |
| Ages 14–18 | `stage:fire` |
| Ages 18+ | `stage:university` |
| Goal: Diploma | `goal:diploma` |
| Goal: Microcredentials | `goal:microcredential` |
| Goal: Full pipeline | `goal:pipeline` |
| GCB: No exposure | `gcb:intro` |
| GCB: Advanced | `gcb:advanced` |
| State: Georgia | `state:GA` + `compliance:filing-required` |
| State: Pennsylvania | `state:PA` + `compliance:filing-required` |
| State: Delaware | `state:DE` + `compliance:home-state` |
| All others | `state:[XX]` + `compliance:standard` |

---

## Klaviyo Integration

Quiz Kit syncs quiz responses to Klaviyo as profile properties.
This enables segmented email flows triggered by quiz completion.

### Flows to Build in Klaviyo

| Flow | Trigger | Content |
|---|---|---|
| Mirror Welcome | Tag: `stage:mirror` | Mirror bundle welcome + curriculum overview |
| Water Welcome | Tag: `stage:water` | Water bundle welcome + curriculum overview |
| Fire Welcome | Tag: `stage:fire` | Fire bundle + dual enrollment details |
| Compliance Alert | Tag: `compliance:filing-required` | State-specific filing instructions + templates |
| Delaware Welcome | Tag: `state:DE` | Simplified compliance card + dashboard access |
| Pipeline Vision | Tag: `goal:pipeline` | Full K–PhD pipeline visual email sequence |
| Waitlist Nurture | Pre-K result | Monthly curriculum preview until age 5 |

---

## Parent Dashboard Connection

On quiz completion + product purchase:

