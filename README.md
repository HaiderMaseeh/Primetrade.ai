# 📊 Trader Performance vs Market Sentiment Analysis

## 📌 Objective

This project analyzes how market sentiment (Fear, Greed, Neutral) influences trader behavior and profitability on Hyperliquid.

The goal is to uncover actionable insights that can improve trading strategies, risk management, and platform design.

---

## 📊 Datasets

### 1. Bitcoin Fear & Greed Index

* Daily sentiment classification (Fear / Greed / Neutral)
* 2,600+ records

### 2. Hyperliquid Trader Data

* 211,000+ trades
* Features include: account, execution price, size, side, leverage, closed PnL, timestamp

---

## ⚙️ Methodology

### 🔹 Data Preparation

* Loaded and validated both datasets (no nulls or duplicates)
* Converted timestamps to daily granularity
* Merged datasets on date
* Filled missing sentiment values using forward-fill (last known sentiment)

---

### 🔹 Feature Engineering

| Feature       | Description                            |
| ------------- | -------------------------------------- |
| `is_profit`   | Trade result (PnL > 0)                 |
| `abs_size`    | Absolute trade size in USD             |
| `is_long`     | BUY → Long position                    |
| `trader_freq` | Frequent vs Infrequent (median split)  |
| `risk_group`  | High vs Low risk (based on trade size) |
| `consistency` | Winner vs Loser (based on total PnL)   |

---

### 🔹 Key Metrics

* Average PnL per trade
* Win rate
* Trade frequency
* Position size
* Long/Short ratio

---

## 📈 Key Insights

### 1. 📈 Greed Markets Drive Highest Profitability

* Mean PnL during Greed ≈ **2x higher than Fear**
* Win rate peaks near **49% in Extreme Greed**

👉 Traders perform best in bullish conditions.

---

### 2. ⚠️ Fear Triggers Overtrading & Emotional Decisions

* Trade frequency spikes **2.2x during Fear**
* Largest position sizes observed during Fear

👉 Indicates panic-driven behavior and poor discipline.

---

### 3. 💰 Infrequent Traders Outperform

* Infrequent traders earn **2.3x higher PnL per trade**
* Frequent traders show lower efficiency despite higher activity

👉 “Trade less, earn more” is supported by data.

---

### 4. 🔥 High-Risk Traders Generate Highest Returns

* High-risk traders outperform in both Fear and Greed
* However, returns are volatile and require discipline

---

### 5. 📉 Losses Concentrate During Fear

* Losing traders experience largest losses during Fear
* Driven by overtrading + oversized positions

---

## 🧠 Strategy Recommendations

### 🔹 Strategy 1: Sentiment-Aware Risk Control

* During **Fear**:

  * Reduce leverage by **20–30%**
  * Limit number of trades per day
  * Avoid increasing position size

👉 Prevents emotional and panic-driven losses.

---

### 🔹 Strategy 2: Opportunistic Trading During Greed

* During **Greed**:

  * Increase participation in trending markets
  * Use moderate-to-high leverage selectively
  * Favor momentum-based strategies

👉 Capitalize on higher win probability and profitability.

---

### 🔹 Strategy 3: Quality Over Quantity Trading

* Reduce excessive trading frequency
* Focus on high-confidence setups

👉 Infrequent traders show significantly higher efficiency.

---

### 🔹 Strategy 4: Segment-Based Risk Management

* High-risk traders:

  * Provide advanced tools (leverage, analytics)
* Low-risk / losing traders:

  * Restrict leverage during Fear
  * Add warning systems for large trades

---

## 📊 Outputs

The following visualizations are included:

* PnL distribution by sentiment
* Win rate by sentiment
* Trade behavior analysis (frequency, size)
* Trader segmentation insights

---

## ▶️ How to Run

### 1. Install Dependencies

```bash
pip install -r requirements.txt
```

---

### 2. Run Analysis Notebook (Core Insights)

```bash
jupyter notebook Notebook/analysis.ipynb
```

This notebook includes:

* Data cleaning & merging
* Feature engineering
* Sentiment vs trader behavior analysis
* Visualizations & key insights

---

### 3. Run Machine Learning Notebook (Bonus)

```bash
jupyter notebook Notebook/model_training.ipynb
```

This notebook includes:

* Feature preparation for modeling
* Model training (e.g., Random Forest )
* Prediction of trader profitability / behavior

---

### 📌 Recommended Order

Run notebooks in this sequence:

1. `analysis.ipynb` → Understand data & insights
2. `model_training.ipynb` → Explore predictive modeling

---


---

## 🧾 Conclusion

Market sentiment plays a critical role in shaping trader behavior and performance.

* Fear leads to irrational, high-risk trading
* Greed provides structured opportunities for profit
* Strategic alignment with sentiment can significantly improve outcomes

---
