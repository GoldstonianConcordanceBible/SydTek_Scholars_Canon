# SydTek Scholars $GCB Pricing Options
## Chunk 8 of 10 — Shopify Live Converter Block

/docs/payment-system/shopify-live-gcb-converter.md

---

# Purpose

This document outlines the Shopify page block that displays:

```text
USD tuition price

Live $GCB price

Estimated $GCB required

Treasury wallet

Verification instructions
```

---

# Recommended Placement

Add this block to:

```text
Product pages

Course pages

Certificate pages

Curriculum bundle pages

Pay with $GCB page
```

Place it directly below the standard Shopify price.

---

# Display Example

```text
Pay with $GCB

Tuition:
$99 USD

Live $GCB Price:
$0.00000395

Estimated Amount Due:
25,063,291 $GCB

Payment Wallet:
Phantom Wallet

Treasury Wallet:
[INSERT TREASURY WALLET ADDRESS]

Price Timestamp:
[Auto-generated timestamp]
```

---

# Basic Custom Liquid Block

Paste into:

```text
Shopify Admin
→ Online Store
→ Themes
→ Customize
→ Product Template
→ Add Section
→ Custom Liquid
```

---

# Starter Code

```liquid
<div class="gcb-payment-box">
  <h3>Pay with $GCB</h3>

  <p><strong>Tuition:</strong> {{ product.price | money }}</p>

  <p><strong>Live $GCB Price:</strong> 
    <span id="gcb-price">Loading...</span>
  </p>

  <p><strong>Estimated $GCB Required:</strong> 
    <span id="gcb-required">Loading...</span>
  </p>

  <p><strong>Payment Wallet:</strong> Phantom Wallet</p>

  <p><strong>Treasury Wallet:</strong></p>
  <code>[INSERT TREASURY WALLET ADDRESS]</code>

  <p><strong>Price Timestamp:</strong> 
    <span id="gcb-timestamp">Loading...</span>
  </p>

  <p>
    Tuition is denominated in USD. $GCB payment amounts are calculated using the live market price at the time of on-chain confirmation.
  </p>
</div>

<script>
  const usdPrice = {{ product.price | divided_by: 100.0 }};

  async function loadGcbPrice() {
    try {
      /*
        Replace this placeholder URL with the final $GCB price API endpoint.
        Examples:
        - DEX Screener token pair API
        - Birdeye token price API
        - Jupiter token price API
        - Custom SydTek price oracle endpoint
      */

      const response = await fetch('[INSERT_GCB_PRICE_API_ENDPOINT]');
      const data = await response.json();

      /*
        Update this line depending on the API response format.
        Example:
        const gcbPrice = data.priceUsd;
      */

      const gcbPrice = Number(data.priceUsd);

      const requiredGcb = usdPrice / gcbPrice;

      document.getElementById('gcb-price').innerText =
        '$' + gcbPrice.toFixed(8);

      document.getElementById('gcb-required').innerText =
        Math.ceil(requiredGcb).toLocaleString() + ' $GCB';

      document.getElementById('gcb-timestamp').innerText =
        new Date().toLocaleString();

    } catch (error) {
      document.getElementById('gcb-price').innerText =
        'Price unavailable';

      document.getElementById('gcb-required').innerText =
        'Use manual verification';

      document.getElementById('gcb-timestamp').innerText =
        'Unavailable';
    }
  }

  loadGcbPrice();
  setInterval(loadGcbPrice, 60000);
</script>

<style>
  .gcb-payment-box {
    border: 1px solid #ddd;
    padding: 16px;
    margin-top: 20px;
    border-radius: 12px;
  }

  .gcb-payment-box code {
    display: block;
    word-break: break-all;
    padding: 10px;
    background: #f6f6f6;
    border-radius: 8px;
  }
</style>
```

---

# Price Feed Options

Use one of these sources:

```text
DEX Screener

Birdeye

Jupiter

Helius

Custom Treasury Oracle
```

---

# Minimum Required API Fields

The converter needs:

```text
Token symbol

Token address

USD price

Timestamp

Source

Liquidity pair
```

---

# Recommended Display Warning

```text
The displayed $GCB amount is an estimate. The final amount is validated using the market price and blockchain timestamp at the time your transaction confirms on-chain.
```

---

# Manual Fallback

If the price feed fails, display:

```text
Live price unavailable.

Please contact SydTek Scholars support or use the latest posted $GCB tuition rate before sending payment.
```

---

# Future Upgrade

Later, this block should generate:

```text
Solana Pay QR code

Pre-filled payment amount

Treasury wallet

Order number memo

Auto-verification status
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

Solana Pay Automation     ██░░░░░░░░ 20%

Credential Automation     ░░░░░░░░░░ 0%
```