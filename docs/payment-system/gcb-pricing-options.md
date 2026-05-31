# SydTek Scholars $GCB Pricing Options
## Chunk 1 of 10 — Pricing Architecture

/docs/payment-system/gcb-pricing-options.md

---

## Core Principle

SydTek Scholars should price tuition in USD while allowing students to pay the equivalent value in $GCB.

```text
USD = accounting value

$GCB = payment rail

Blockchain timestamp = price proof

Transaction hash = receipt
```

---

## Recommended Default

```text
Tuition: $99 USD

Live $GCB Price: $0.00000395

Required Payment: 25,063,291 $GCB
```

---

## Formula

```text
Required $GCB = USD Tuition ÷ Live $GCB Price
```

---

## Four Pricing Models

```text
1. USD Reference Model

2. USD + Live $GCB Conversion

3. Fixed $GCB Tuition

4. Membership / Treasury Model
```

---

## Best Phase 1 Choice

```text
USD + Live $GCB Conversion
```

### Why

```text
Stable accounting

Simple Shopify setup

Clear student pricing

Works with manual verification

Supports future automation
```

---

## Policy Language

SydTek Scholars tuition and fees are denominated in U.S. Dollars. Students may satisfy eligible payments using $GCB. The required $GCB amount is calculated using the live market price at the time of on-chain transaction confirmation. The blockchain transaction hash and timestamp serve as the official proof of payment.

---

## Phase I Architecture

```text
Student
    ↓
Shopify Store
    ↓
Select Course
    ↓
Live $GCB Price Feed
    ↓
Tuition Conversion
    ↓
Pay with $GCB
    ↓
Treasury Wallet
    ↓
Transaction Verification
    ↓
Course Access
    ↓
Credential Registry
```

---

## Repository Structure

```text
/docs/payment-system/

gcb-pricing-options.md

payment-policy.md

student-payment-guide.md

wallet-verification.md

shopify-gcb-integration.md
```

---

## Repo Status

```text
Pricing Architecture     ██████████ 100%

Shopify Manual Setup     ██░░░░░░░░ 20%

Live Converter           ██░░░░░░░░ 20%

Solana Pay Automation    ░░░░░░░░░░ 0%
```