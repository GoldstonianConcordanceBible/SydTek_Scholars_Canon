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

