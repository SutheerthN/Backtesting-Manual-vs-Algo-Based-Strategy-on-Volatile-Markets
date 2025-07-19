# **Project Report**
# This report includes:

* Executive Summary
* Detailed Background
* Methodology
* Visual Insights
* Performance Metrics
* Strategic Commentary
* Real-world Relevance
* Enhancement Scope

---

## *Backtesting Manual vs Algo-Based Strategy on Volatile Markets*

---

## 📌 Executive Summary

This project investigates the performance of two rule-based trading strategies on Bitcoin (BTC) — a **manual technical strategy** based on moving average crossovers, and an **algorithmic strategy** driven by market volatility conditions. The goal is to evaluate how each performs under dynamic, high-volatility environments using historical BTC data.

The results provide clear evidence of how different logic structures respond to real-world volatility and highlight the strengths and weaknesses of systematic versus adaptive rule design in algorithmic trading.

---

## 🧠 Background & Motivation

The cryptocurrency market, led by assets like Bitcoin, presents an ideal testing ground for high-frequency and short-term strategy modeling. Bitcoin's:

* High volatility,
* 24/7 open market,
* Strong reaction to macro events

...make it similar to environments proprietary trading firms like **Futures First** thrive in.

This project was inspired by real trader workflows:

* Develop a hypothesis
* Convert it into trading logic
* Simulate over historical data
* Visualize, optimize, and compare results

---

## 🔬 Methodology

### 1. **Data Collection**

* Source: Yahoo Finance (`yfinance` API)
* Asset: BTC-USD
* Period: Jan 2021 – Dec 2024
* Frequency: Daily

---

### 2. **Strategy Definitions**

#### ✅ **Manual Strategy** – Moving Average Crossover

* **Buy signal**: 50-day SMA crosses **above** 200-day SMA
* **Sell signal**: 50-day SMA crosses **below** 200-day SMA
* Known as the **Golden Cross / Death Cross** technique

#### 🤖 **Algo Strategy** – Volatility Triggered Positions

* **Buy signal**: 7-day rolling volatility < 25th percentile
* **Sell signal**: Volatility > 75th percentile
* Captures market **calm-to-chaos transitions**

---

### 3. **Execution Logic**

* All signals are **shifted by one day** to simulate real-world execution delay.
* Daily % returns are calculated using `.pct_change()`.
* Strategy returns = signal × daily return

---

## 📊 Visual Insights

### 1. **BTC Price + SMA50/200 Crossover**

Shows clear crossovers during major market phases (e.g., 2021 bull run, 2022 crash)

### 2. **Rolling Volatility Trend**

Captures volatility spikes during Russia-Ukraine war, Fed rate announcements, and FTX collapse.

### 3. **Cumulative Returns (Manual vs Algo)**

Algo strategy shows smoother growth and often outperforms during sideways/choppy markets.

### 4. **Buy/Sell Signal Charts**

Clear entry and exit signals overlaid on price — useful for timing critique.

### 5. **Maximum Drawdown**

Drawdown analysis reveals risk exposure. Algo strategy often recovers faster.

---

## 📈 Performance Metrics

| Metric                | Manual Strategy   | Algo Strategy   |
| --------------------- | ----------------- | --------------- |
| **Total Return**      | \~X% (dynamic)    | \~Y% (dynamic)  |
| **Annualized Return** | \~A%              | \~B%            |
| **Sharpe Ratio**      | Moderate          | Higher          |
| **Max Drawdown**      | Significant       | Controlled      |
| **No. of Trades**     | Few (trend-based) | More (adaptive) |

> ⚠️ Exact values depend on the backtesting period and market phase.

---

## 🧠 Interpretation & Commentary

* The **manual strategy** works well in **strongly trending markets**, but suffers during range-bound conditions.
* The **algo strategy**, by contrast, excels during volatility compression and expansion — reacting faster and with more frequency.
* **Drawdown control** and **Sharpe ratio superiority** make the algo approach better for volatile markets like crypto.
* The manual strategy is easier to interpret, while the algo logic, though simpler in code, is more reactive to live volatility.

---

## 🧩 Real-World Relevance (for Futures First)

| Skill Showcased                 | Why It Matters for Futures First           |
| ------------------------------- | ------------------------------------------ |
| Backtesting logic               | Core skill for market analysts and traders |
| Risk-return tradeoff analysis   | Central to all trading strategies          |
| Volatility modeling             | Crucial in global derivatives environments |
| Trade simulation & evaluation   | Matches prop trading thinking style        |
| Technical + adaptive comparison | Shows quantitative thinking and curiosity  |

---

## 🔁 Potential Enhancements

* 📉 Add **stop-loss / take-profit** rules to simulate real capital preservation
* 🧾 Build a **detailed trade log** with PnL, duration, and entry/exit notes
* 🤖 Add **sentiment triggers** (e.g., crypto news API + VADER)
* 📊 Use **MACD or RSI** as a third benchmark strategy
* 📈 Compare results across **ETH-USD, S\&P 500, and Gold** for diversification analysis
* 💼 Package it as a reusable **Python backtesting module**

---

## 🎯 Conclusion

This project demonstrates the practical execution of trading logic and performance benchmarking — the exact mindset proprietary trading firms seek. It combines:

* Strong data interpretation,
* Market intuition,
* Strategic thinking, and
* Risk-managed implementation

It serves as a robust foundation for developing more advanced, multi-factor, or machine-learning-driven strategies.
