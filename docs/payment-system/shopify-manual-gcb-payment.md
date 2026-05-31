# SydTek Scholars $GCB Pricing Options
## Chunk 3 of 10 — Shopify Manual Payment Method Setup

/docs/payment-system/shopify-manual-gcb-payment.md

---

# Purpose

This tutorial explains how to add $GCB as a manual payment option inside Shopify.

This is the fastest Phase I method for accepting $GCB tuition payments before building full Solana Pay automation.

---

# Step 1 — Open Shopify Payments

Go to:

```text
Shopify Admin
    ↓
Settings
    ↓
Payments
```

---

# Step 2 — Add Manual Payment Method

Scroll to:

```text
Manual Payment Methods
```

Select:

```text
Add manual payment method
```

Then choose:

```text
Create custom payment method
```

---

# Step 3 — Name the Payment Method

Use:

```text
Pay with $GCB via Phantom Wallet
```

---

# Step 4 — Add Customer Instructions

Copy and paste this into Shopify:

```text
Thank you for choosing to pay with $GCB.

Your tuition is denominated in U.S. Dollars. The required $GCB amount is calculated using the live $GCB market price at the time your transaction is confirmed on-chain.

Payment Steps:

1. Open your Phantom Wallet.

2. Send the required $GCB amount to the official SydTek Scholars treasury wallet.

Treasury Wallet:
[INSERT TREASURY WALLET ADDRESS]

3. Copy your transaction hash from Phantom or Solscan.

4. Submit your transaction hash using the verification form below.

Verification Form:
[INSERT VERIFICATION FORM LINK]

5. Your enrollment, certificate, or course access will be activated after payment verification.

Important:

The blockchain timestamp and transaction hash serve as the official proof of payment.

Digital asset payments are final once confirmed on-chain.

Incorrect wallet transfers may not be recoverable.
```

---

# Step 5 — Add Payment Policy

Add this to the product description, checkout instructions, and policy page:

```text
SydTek Scholars accepts $GCB as an approved digital asset payment method for eligible tuition, books, certificates, curriculum, and educational products.

All prices remain denominated in U.S. Dollars. When paying with $GCB, the required token amount is calculated using the live market value of $GCB at the time of on-chain confirmation.

The transaction hash and blockchain timestamp serve as the official payment record.
```

---

# Step 6 — Create Verification Form

Use one of the following:

```text
Google Form

Typeform

Shopify Contact Form

Airtable Form

Tally Form
```

Required fields:

```text
Full Name

Email Address

Shopify Order Number

Course or Product Purchased

USD Tuition Amount

$GCB Amount Sent

Transaction Hash

Wallet Address Used

Date Submitted
```

---

# Step 7 — Manual Verification Workflow

```text
Student submits transaction hash
        ↓
Admin opens Solscan
        ↓
Admin verifies treasury wallet received $GCB
        ↓
Admin checks timestamp
        ↓
Admin confirms amount
        ↓
Admin marks Shopify order as paid
        ↓
Student receives course access
```

---

# Step 8 — Shopify Order Tagging

After verification, tag the order:

```text
GCB-PAYMENT

PHANTOM-WALLET

ONCHAIN-VERIFIED

TUITION-PAID
```

Optional tags:

```text
COURSE-ACCESS-GRANTED

CERTIFICATE-ELIGIBLE

CREDENTIAL-REGISTRY
```

---

# Step 9 — Email Confirmation Template

```text
Subject:
Your SydTek Scholars $GCB Payment Has Been Verified

Body:
Hello [Student Name],

Your $GCB payment for [Course/Product Name] has been verified.

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

Your course, curriculum, certificate, or credential access has now been activated.

Thank you for participating in the SydTek Scholars ecosystem.

SydTek Scholars
Goldstonian Concordance Bible (GCB) Ecosystem
```

---

# Step 10 — Phase I Status

```text
Manual Payment Setup      ██████████ 100%

Verification Workflow     ████████░░ 80%

Auto Price Feed           ██░░░░░░░░ 20%

Solana Pay Checkout       ░░░░░░░░░░ 0%
```

---

# Final Phase I Rule

```text
Do not mark an order paid until:

1. The transaction hash is valid.

2. The treasury wallet received the correct $GCB amount.

3. The transaction timestamp matches the price calculation window.

4. The student’s Shopify order number matches the verification form.
```