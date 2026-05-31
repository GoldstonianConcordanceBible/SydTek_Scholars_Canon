# SydTek Scholars $GCB Pricing Options
## Chunk 5 of 10 — Treasury Wallet Verification Engine & Solscan Tutorial

/docs/payment-system/gcb-wallet-verification.md

---

# Purpose

This document explains how SydTek Scholars verifies $GCB tuition payments after a student sends tokens from Phantom Wallet.

The goal is to confirm:

```text
Correct wallet

Correct token

Correct amount

Correct timestamp

Correct order number

Correct student
```

---

# Core Verification Rule

A $GCB payment is not complete until the treasury wallet receives the correct $GCB amount and the transaction is confirmed on-chain.

```text
Transaction hash = receipt

Blockchain timestamp = payment time

Treasury wallet = receiving account

$GCB amount = tuition value
```

---

# Required Verification Fields

Each student must submit:

```text
Full Name

Email Address

Shopify Order Number

Course or Product Purchased

USD Tuition Amount

$GCB Amount Sent

Student Wallet Address

Transaction Hash

Date Submitted
```

---

# Admin Verification Workflow

```text
Student submits transaction hash
        ↓
Admin opens Solscan
        ↓
Admin searches transaction hash
        ↓
Admin confirms token is $GCB
        ↓
Admin confirms receiver is treasury wallet
        ↓
Admin confirms amount received
        ↓
Admin checks timestamp
        ↓
Admin compares to Shopify order
        ↓
Admin marks order as paid
        ↓
Admin grants access
```

---

# Solscan Tutorial

## Step 1 — Open Solscan

Go to:

```text
https://solscan.io
```

---

## Step 2 — Paste Transaction Hash

Use the search bar.

Paste:

```text
Student transaction hash
```

---

## Step 3 — Confirm Transaction Status

Look for:

```text
Status: Success
```

Do not approve if status shows:

```text
Failed

Dropped

Unknown

Pending
```

---

## Step 4 — Confirm Token

Verify the token transferred is:

```text
$GCB
```

Do not approve if the student sent:

```text
SOL

USDC

Wrong token

Fake copy token
```

---

## Step 5 — Confirm Treasury Wallet

Receiver must match:

```text
Official SydTek Scholars Treasury Wallet:

[INSERT TREASURY WALLET ADDRESS]
```

If the wallet does not match, payment is not verified.

---

## Step 6 — Confirm Amount

Example:

```text
Shopify Tuition:
$99 USD

GCB Price:
$0.00000395

Required:
25,063,291 GCB
```

Solscan should show at least:

```text
25,063,291 GCB received
```

---

# Underpayment Rule

If the student sends less than required:

```text
Payment Status:
Underpaid
```

Admin response:

```text
Please send the remaining $GCB balance and submit the second transaction hash.
```

---

# Overpayment Rule

If the student sends more than required:

```text
Payment Status:
Overpaid
```

Recommended policy:

```text
Overpayments below a small threshold may be retained as voluntary treasury support.

Large overpayments may be reviewed manually.
```

---

# Timestamp Rule

The transaction timestamp must be used to determine the accepted price.

Example:

```text
Order Created:
3:00 PM

Student Paid:
3:12 PM

Transaction Confirmed:
3:13 PM

Price used:
3:13 PM market price
```

The confirmed on-chain timestamp is the official payment time.

---

# Verification Spreadsheet Columns

Create a Google Sheet or Airtable with:

```text
Date Submitted

Student Name

Email

Shopify Order Number

Course

USD Price

GCB Price Used

Required GCB

Received GCB

Student Wallet

Treasury Wallet

Transaction Hash

Timestamp

Solscan Link

Status

Admin Initials
```

---

# Status Labels

Use these statuses:

```text
Pending Review

Verified

Underpaid

Overpaid

Wrong Wallet

Wrong Token

Failed Transaction

Refund Review

Access Granted
```

---

# Shopify Tags After Verification

Apply these Shopify order tags:

```text
GCB-PAYMENT

ONCHAIN-VERIFIED

SOLSCAN-CONFIRMED

TUITION-PAID

ACCESS-GRANTED
```

---

# Access Granting

After verification, complete one of the following:

```text
Send digital download

Unlock course

Add student to LearnWorlds

Email certificate instructions

Add student to credential registry
```

---

# Email Template: Verified Payment

```text
Subject:
Your $GCB Tuition Payment Has Been Verified

Hello [Student Name],

Your $GCB payment for [Course/Product] has been verified.

Order Number:
[Order Number]

Transaction Hash:
[Transaction Hash]

Blockchain Timestamp:
[Timestamp]

USD Tuition Value:
[$ Amount]

$GCB Amount Received:
[GCB Amount]

Your access has now been activated.

Thank you for participating in the SydTek Scholars ecosystem.

SydTek Scholars
Goldstonian Concordance Bible (GCB) Ecosystem
```

---

# Email Template: Underpaid Payment

```text
Subject:
Additional $GCB Required to Complete Your Payment

Hello [Student Name],

We received your $GCB transaction for [Course/Product], but the amount received was less than the required tuition amount.

Order Number:
[Order Number]

Required:
[Required GCB]

Received:
[Received GCB]

Remaining Balance:
[Remaining GCB]

Please send the remaining balance to the official treasury wallet and submit the new transaction hash.

SydTek Scholars
```

---

# Security Rules

Never approve a payment unless:

```text
Transaction status is successful

Token is confirmed as $GCB

Receiver is the official treasury wallet

Amount meets or exceeds required tuition

Timestamp is recorded

Shopify order number matches the student
```

---

# Repo Status

```text
Pricing Architecture      ██████████ 100%

Shopify Manual Setup      ██████████ 100%

Live Price Calculator     ██████████ 100%

Wallet Verification       ██████████ 100%

Solana Pay Automation     ░░░░░░░░░░ 0%

Credential Automation     ░░░░░░░░░░ 0%
```