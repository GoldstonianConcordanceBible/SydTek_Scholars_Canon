# SydTek Scholars $GCB Pricing Options
## Chunk 4 of 10 — Live $GCB Price Feed & Tuition Calculator

/docs/payment-system/gcb-price-feed.md

---

# Purpose

This document explains how to display a live $GCB price and automatically calculate tuition amounts on Shopify.

Goal:

```text
Student sees:

Course Price: $99 USD

Current GCB Price:
$0.00000395

Required GCB:
25,063,291
```

without manual calculations.

---

# Phase I Architecture

```text
Price Source
        ↓
GCB Market Price
        ↓
Shopify Product Page
        ↓
Tuition Calculator
        ↓
Student Payment
```

---

# Option A
## Manual Daily Update

Recommended for launch.

---

### Example

Create a product block:

```text
Current GCB Price

$0.00000395

Last Updated:
May 31, 2026
```

Then calculate:

```text
$99 ÷ 0.00000395
=
25,063,291 GCB
```

Update daily.

---

### Advantages

```text
Simple

No coding

No API

Can launch today
```

---

### Disadvantages

```text
Manual updates

Not real-time
```

---

# Option B
## Automated Price Feed

Recommended for Phase II.

---

### Architecture

```text
DEX Price Feed
        ↓
API
        ↓
Shopify Theme Block
        ↓
Live Calculator
```

---

### Display Example

```text
Tuition

$99 USD

Live GCB Price

$0.00000401

Required

24,688,279 GCB
```

---

# Calculator Formula

```text
Required GCB

=

USD Tuition

÷

Current GCB Price
```

---

# Example Calculations

## Certificate

```text
$25

÷

$0.00000395

=

6,329,114 GCB
```

---

## Course

```text
$99

÷

$0.00000395

=

25,063,291 GCB
```

---

## Curriculum Bundle

```text
$299

÷

$0.00000395

=

75,696,203 GCB
```

---

# Shopify Placement

---

## Product Page

Place directly below price.

Example:

```text
$99.00

or

25,063,291 GCB

(Current Market Value)
```

---

## Dedicated Tuition Page

Create:

```text
/pages/pay-with-gcb
```

Content:

```text
Live Price

Calculator

Treasury Wallet

Verification Form

Instructions
```

---

## Course Collection Page

Create:

```text
/collections/pay-with-gcb
```

Display:

```text
All products accepting GCB
```

---

# Price Timestamp Policy

Every calculation should record:

```text
Transaction Hash

Block Number

Timestamp

Price Used

Amount Received
```

---

# Verification Example

```text
Student Pays

25,063,291 GCB

Timestamp:
5/31/2026
3:15 PM

Market Price:
$0.00000395

USD Equivalent:
$99
```

Payment verified.

---

# Future Enhancement

Instead of entering:

```text
25,063,291
```

students scan:

```text
QR Code
```

generated automatically.

---

# Repository Structure

```text
/apps/gcb-price-feed/

README.md

price-api.md

shopify-calculator.md

verification-engine.md
```

---

# Completion Status

```text
Pricing Architecture      ██████████

Shopify Payment Method    ██████████

Price Feed Strategy       ██████████

Wallet Verification       ███░░░░░░░

Solana Pay Checkout       ░░░░░░░░░░

Credential Automation     ░░░░░░░░░░
```

---

# Deliverable

After Chunk 4 is complete, students will be able to:

```text
View tuition

View current GCB value

Calculate required GCB

Send payment

Submit transaction hash
```

without contacting an administrator.