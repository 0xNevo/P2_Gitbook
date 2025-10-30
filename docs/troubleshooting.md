# Troubleshooting Guide

Having issues using **Predictive Perpetuals (P²)**?\
This guide covers the most common problems traders and developers might encounter — and how to solve them quickly.

***

## ⚙️ 1. Wallet & Connection Issues

### ❌ Problem: My wallet won’t connect

**Possible Causes**

* Browser extension not detected
* Unsupported wallet or outdated version
* Wallet network mismatch

**Quick Fix**

1. Refresh the page and reopen your wallet.
2. Ensure you’re on the **Binance Mainnet** or the designated **Testnet**.
3. Clear browser cache or try an incognito window.
4. If using mobile, open the site directly from the wallet’s in-app browser.

**Still not working?**\
→ Visit our support Telegram: [Join Community Chat](troubleshooting.md)

***

## 🪙 2. Transaction or Trade Fails

### ❌ Problem: “Transaction simulation failed”

**Possible Causes**

* Insufficient BNB for gas
* Margin too low for leverage chosen
* Network congestion on Binance RPC

**Quick Fix**

1. Check that you have at least **0.001 BNB** for transaction fees.
2. Reduce leverage or margin slightly and retry.
3. Try again in 30–60 seconds — the RPC node might be under load.
4. Switch to another RPC endpoint if supported by your wallet.

***

### ❌ Problem: “Transaction pending” or “Stuck confirmation”

**Quick Fix**

* Go to your wallet and check **Recent Transactions**.
* If status is _“pending”_, cancel and resend with a slightly higher priority.
* For repeated issues, use Solscan or Binance Explorer to confirm status manually.

***

## 📈 3. PnL or Funding Not Updating

### ❌ Problem: My unrealized PnL isn’t refreshing

**Possible Causes**

* Temporary desync between price oracle and frontend
* Cached browser data or inactive websocket feed

**Quick Fix**

1. Refresh your browser or reconnect wallet.
2. Check Binance network status → [Binance Status](https://status.binance.com/)
3. If using mobile, switch networks and reconnect.
4. In rare cases, wait 1–2 minutes for AI engine recalibration.

***

### ❌ Problem: Funding rates look incorrect

**Explanation** Funding in P² is **AI-adjusted** — not constant.\
Rates may temporarily fluctuate based on:

* Volatility
* Liquidity imbalance
* AI risk model updates

If the change is large or unexpected: → Check [AI Risk & Funding Page](4_ai-engine/risk-and-funding-management.md)

***

## 🧠 4. AI Engine & Oracle Sync Errors

### ❌ Problem: “AI Engine Unavailable” message

**Possible Causes**

* Backend AI module undergoing update or maintenance
* Oracle source temporarily desynced

**Quick Fix**

1. Wait a few minutes — AI engine automatically restarts.
2. Retry after refreshing the page.
3. Check official [Status Announcements](troubleshooting.md) for scheduled maintenance.

***

### ❌ Problem: Probability Index Not Updating

**Quick Fix**

* Clear browser cache.
* Switch to a different market pair.
* Confirm oracle feed via Binance Explorer.
* If it persists, report the market ID to support.

***

## 🔐 5. Security & Safety

### ⚠️ Problem: Suspected phishing or fake site

**Quick Fix** Always verify you’re using the **official domain**:

> ✅ `https://predictiveperpetuals.io`

Never share private keys or seed phrases — admins will never ask for them.

If you encounter fake sites: → Report to [security@predictiveperpetuals.io](mailto:security@predictiveperpetuals.io)

***

## 📞 6. Still Need Help?

If you’ve tried everything and it’s still not working:

* 🧩 [Join our Telegram Community](troubleshooting.md)
* 🐦 [Follow on X (Twitter)](troubleshooting.md)
* 📘 [Read the Full Docs](../)
* 📧 Email Support: **support@predictiveperpetuals.io**

***

### 💡 Tip

Before opening a ticket, always include:

* Wallet address (never private key)
* Transaction signature (if applicable)
* Screenshot or error message

This helps us resolve your issue faster.
