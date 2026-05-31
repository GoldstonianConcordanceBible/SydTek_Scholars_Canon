# SydTek Scholars $GCB Pricing Options
## Chunk 9 of 10 — Solana Pay Automation Roadmap

/docs/payment-system/solana-pay-gcb-automation.md

---

# Purpose

This document explains how SydTek Scholars can move from manual $GCB verification to automated Solana Pay checkout.

The goal is:

```text
Student selects course
        ↓
Shopify displays $GCB amount
        ↓
Student scans QR code
        ↓
Phantom opens
        ↓
Student approves payment
        ↓
Transaction confirms on-chain
        ↓
Shopify order updates
        ↓
Course access unlocks
```

---

# Phase I vs Phase II

## Phase I

```text
Manual Shopify Payment Method

Manual Phantom Transfer

Manual Transaction Hash Review
```

## Phase II

```text
Solana Pay QR Code

Auto Amount Calculation

Auto Transaction Verification

Auto Enrollment Trigger
```

---

# Core Components

```text
Shopify Product

$GCB Price Feed

Solana Pay QR Generator

Treasury Wallet

Transaction Listener

Shopify Order Tagger

Course Access Trigger
```

---

# Solana Pay Payment Request

Each payment request should include:

```text
Treasury wallet

$GCB token mint address

Required token amount

Order number

Product ID

Student email

Timestamp
```

---

# Example Payment Metadata

```json
{
  "order_number": "SYD-1001",
  "product": "AAI-301 Artificial Intelligence Foundations",
  "usd_price": "99.00",
  "gcb_price": "0.00000395",
  "required_gcb": "25063291",
  "token": "$GCB",
  "network": "Solana",
  "payment_wallet": "Phantom",
  "treasury_wallet": "[INSERT TREASURY WALLET]",
  "status": "pending"
}
```

---

# Automation Workflow

```text
Student clicks Pay with $GCB
        ↓
System calculates required GCB
        ↓
System creates Solana Pay QR
        ↓
Student scans with Phantom
        ↓
Payment goes to treasury wallet
        ↓
System detects transaction
        ↓
System verifies token and amount
        ↓
System records timestamp
        ↓
System marks Shopify order as paid
        ↓
System grants course access
```

---

# Verification Logic

The system must confirm:

```text
Transaction status = success

Token = $GCB

Receiver = treasury wallet

Amount >= required GCB

Timestamp exists

Order metadata matches

No duplicate transaction hash
```

---

# Shopify Automation Tags

After verification, apply:

```text
GCB-PAYMENT

SOLANA-PAY

ONCHAIN-VERIFIED

AUTO-VERIFIED

TUITION-PAID

ACCESS-GRANTED
```

---

# Suggested App Stack

```text
Frontend:
Shopify Theme Extension

Wallet:
Phantom / Solana Pay

Blockchain:
Solana RPC / Helius

Price:
DEX Screener / Jupiter / Birdeye

Backend:
Node.js / Next.js API

Database:
Supabase / Airtable / Firebase

Automation:
Shopify Admin API

Enrollment:
LearnWorlds / Shopify Digital Downloads / Email Trigger
```

---

# Minimum Database Fields

```text
Order ID

Shopify Customer ID

Email

Product ID

USD Price

GCB Price Used

Required GCB

Treasury Wallet

Student Wallet

Transaction Hash

Confirmation Timestamp

Verification Status

Access Status
```

---

# Failure States

```text
Underpaid

Wrong Token

Wrong Wallet

Expired Quote

Duplicate Transaction

Transaction Failed

Price Feed Error

RPC Error

Manual Review Required
```

---

# Expired Quote Rule

Because token prices move, each generated payment quote should expire.

Recommended window:

```text
10 minutes
```

After expiration:

```text
Student must refresh price quote.
```

---

# Audit Record

Every verified order should preserve:

```text
Price source

Price timestamp

Transaction timestamp

Transaction hash

Wallet addresses

USD amount

$GCB amount

Admin/system verifier

Course/product delivered
```

---

# Future Credential Trigger

After payment verification:

```text
Shopify Paid Order
        ↓
Course Access Granted
        ↓
Completion Recorded
        ↓
Credential NFT or Registry Entry
```

---

# Security Notes

Never auto-verify unless:

```text
Token mint address matches official $GCB

Treasury wallet matches official address

Transaction hash is unique

Amount satisfies quote

Payment is confirmed on-chain
```

---

# Progress

```text
Pricing Architecture      ██████████ 100%

Pricing Models            ██████████ 100%

Shopify Manual Setup      ██████████ 100%

Live Converter Block      ██████████ 100%

Wallet Verification       ██████████ 100%

Student Guide             ██████████ 100%

Product Page Copy         ██████████ 100%

Solana Pay Roadmap        ██████████ 100%

Credential Automation     ██░░░░░░░░ 20%
```