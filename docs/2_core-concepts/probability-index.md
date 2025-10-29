# 🎯 Probability Index (P-Index)

The **Probability Index (P-Index)** is the core metric powering **Predictive Perpetuals (P²)**.  
It represents the **market-implied probability** of a future event or directional outcome — dynamically updated in real time using price, sentiment, and AI models.

---

## 🧠 Concept Overview

Traditional perpetuals track **price**, while **Predictive Perpetuals** track **probability**.  
Each market on P² expresses traders’ aggregated belief about a binary outcome:

> “What is the probability this event or condition will occur?”

Examples:
- *BTC > $100k by Q4?* → P-Index = 0.42 (42% implied probability)  
- *SOL outperforms ETH next month?* → P-Index = 0.67 (67% implied probability)

In other words:
> **P-Index ≈ AI-weighted market consensus of truth likelihood.**

---

## ⚙️ How It Works

The P-Index is calculated continuously by the **AI Risk Engine**, combining three major input streams:

| Component | Description | Weight (example) |
|------------|--------------|------------------|
| 📊 Market Microdata | Real-time order flow, funding rate skew, and open interest | 40% |
| 🧠 AI Models | Transformer-based event prediction + reinforcement model calibration | 40% |
| 🛰️ Oracles | External market data and sentiment feeds (X, news, DeFi APIs) | 20% |

Each tick (block), the engine updates:

P_t = α * M_t + β * A_t + γ * O_t


Where:
- `P_t` = probability index at time `t`
- `M_t` = market-derived signal
- `A_t` = AI model signal
- `O_t` = oracle-derived signal
- `α, β, γ` = adaptive weighting coefficients tuned by AI Vault feedback

---

## 📈 Real-Time Adjustments

The P-Index is **not static** — it evolves based on:
- **Trade volume imbalance** (long vs short)
- **Funding rate divergence**
- **Price volatility regimes**
- **AI confidence level**

This dynamic updating ensures each P-Index reflects:
1. Market consensus,
2. Statistical probability, and
3. AI conviction score.

---

## 💡 Example

### Market: *“Will BTC close above $80k this month?”*

| Time | P-Index | Interpretation |
|------|----------|----------------|
| 12:00 UTC | 0.38 | Market gives ~38% chance of yes |
| 14:00 UTC | 0.47 | AI detects momentum; traders buying “yes” |
| 20:00 UTC | 0.62 | P-Index spikes as volume surges and sentiment flips bullish |

At expiry (T):
- If event = true → settles at **1.0**
- If false → settles at **0.0**

Traders long or short on the P-Index gain PnL based on how the index moves toward or away from 1.0.

---

## 🧮 Mark-to-Market Impact

Your position’s unrealized PnL depends on the **change in P-Index**, not the absolute value of the underlying asset.

Example:
> Long 10,000 notional P² contracts at P-Index = 0.45  
> Later P-Index = 0.55 → gain of 0.10 × 10,000 = **1,000 P2USD**

Learn more about how this affects liquidation and margin in  
👉 [Mark-to-Market & Liquidation](./mark-to-market-and-liquidation.md)

---

## 🤖 AI Confidence Layer

Each P-Index is accompanied by an **AI Confidence Score (C-Score)**:
- **0.0–0.3:** Low confidence — volatile, high funding adjustments  
- **0.3–0.7:** Neutral zone — balanced predictive accuracy  
- **0.7–1.0:** High confidence — reduced funding volatility  

The C-Score influences:
- Dynamic funding multipliers  
- AI vault hedging intensity  
- Oracle feed refresh rate

---

## 🔍 API Integration

Developers can fetch the current P-Index via the API:

```bash
GET /v1/markets/:id/probability_index

Response:

{
  "market_id": "BTC_80K_OCT",
  "p_index": 0.58,
  "confidence": 0.71,
  "updated_at": "2025-10-29T14:32:11Z"
}
