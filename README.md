# Crypto Algo Trading Signal System (n8n)

## Overview
This project is an automated crypto trading signal system built using **n8n**.  
It fetches real-time market data, applies a moving-average trading strategy, and sends **Telegram alerts** for actionable signals.

> ⚠️ This system is designed for **paper trading and learning purposes only**.

---

## Workflow Architecture

Manual Trigger  
→ Input Symbol  
→ Binance Market Data API  
→ Trading Strategy (JavaScript)  
→ Signal Filter (BUY / SELL only)  
→ Telegram Alert

---

## Trading Logic
- Uses **short-term and long-term moving averages**
- Generates:
  - **BUY** → Short MA > Long MA
  - **SELL** → Short MA < Long MA
  - **HOLD** → No alert (noise reduction)

---

## Technologies Used
- **n8n** – Workflow automation
- **Binance Public API** – Market data
- **JavaScript** – Trading logic
- **Telegram Bot API** – Alert delivery

---

## Sample Output

```json
{
  "symbol": "BTCUSDT",
  "current_price": 90296.98,
  "short_ma": 90460.79,
  "long_ma": 90429.84,
  "signal": "BUY",
  "timestamp": "2026-01-09T20:43:17Z"
}
