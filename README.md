# Backtesting-Manual-vs-Algo-Based-Strategy-on-Volatile-Market

This project explores how two fundamentally different trading strategies — one traditional and one algorithmic — perform in volatile cryptocurrency markets. We analyze and compare a **moving average crossover strategy** (manual) with a **volatility-based algorithmic strategy**, using Bitcoin (BTC-USD) as the test asset.

The goal: understand how **rule-based trading logic** fares against **volatility-responsive algo models** in a real-world environment marked by sharp swings, global events, and uncertainty.

---

## 💡 Why This Project Matters

Financial markets — especially crypto — are fast, complex, and driven by both technical signals and global sentiment. This project simulates what a **real proprietary trader** (like one at Futures First) would do:
- Test strategies over large datasets
- Quantify risk and return
- Visualize decision signals and timing
- Learn from performance across market conditions

---

## 🧠 Methodology

1. **Data Collection**  
   - Fetched historical BTC-USD price data (2021–2024) using Yahoo Finance API via `yfinance`.

2. **Indicator Calculation**  
   - Calculated 50-day and 200-day **Simple Moving Averages** (SMA) for the manual strategy.
   - Computed **7-day rolling standard deviation** of daily returns as a proxy for market volatility.

3. **Strategy Design**
   - **Manual Strategy**: Buy when SMA50 crosses above SMA200, sell when SMA50 drops below SMA200.
   - **Algo Strategy**: Buy when volatility drops below 25th percentile, sell when it rises above 75th percentile.

4. **Signal Execution**
   - Shifted signals by one day to simulate acting on next day’s open (realistic execution logic).
   - Simulated daily returns based on whether the trader was long/short.

5. **Backtesting and Evaluation**
   - Tracked cumulative returns over time.
   - Calculated key performance metrics:
     - Total Return
     - Annualized Return
     - Sharpe Ratio
     - Max Drawdown

6. **Visualization**
   - Plotted:
     - BTC Price with SMA50/SMA200 crossover
     - 7-day volatility trend
     - Buy/Sell signals on price chart
     - Cumulative returns comparison
     - Maximum drawdown analysis

---

## 🎯 Who Should Care?

- 📊 **Aspiring market analysts** exploring trading logic
- 🤖 **Quant-curious developers** entering finance
- 🧠 **Futures First candidates** wanting to show strategy thinking
- 🔁 **Crypto traders** validating basic ideas before automating

---

> This project bridges the gap between data science and trading strategy — showing how logic, volatility, and disciplined rules can be tested, visualized, and refined.
