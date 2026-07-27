# RegimeShift

## Overview

RegimeShift is a quantitative finance project that detects hidden market regimes using a Hidden Markov Model (HMM) and dynamically reallocates a portfolio across equity, gold and bonds.

---

## Project Objective

The goal of this project is to:

- Detect hidden market regimes (Bull, Bear and Crisis)
- Allocate portfolio weights based on the detected regime
- Compare the strategy with static benchmark portfolios
- Evaluate performance using standard portfolio metrics

---

## Data Source

Historical daily market data was collected using Yahoo Finance (`yfinance`).

Assets used:

- NIFTY 50 (^NSEI)
- Gold ETF (GOLDBEES.NS)
- Bond ETF (SETFNIFBK.NS)
- India VIX (^INDIAVIX)

---

## Feature Engineering

The following features were used for regime detection:

- Daily Returns
- 5-Day Momentum
- 20-Day Momentum
- 20-Day Rolling Volatility
- India VIX

These features capture market trend, risk and investor sentiment.

---

## Hidden Markov Model

A Gaussian Hidden Markov Model with **3 hidden states** was trained.

The three states were interpreted as:

- Bull Market
- Bear Market
- Crisis

State interpretation was based on average return, volatility and VIX.

---

## Walk-Forward Validation

Instead of training once on the entire dataset, the model was repeatedly trained only on historical data and tested on future data.

This prevents look-ahead bias.

---

## Portfolio Allocation

Portfolio weights change according to the detected regime.

Example allocations:

| Regime | NIFTY | Gold | Bonds |
|---------|------:|------:|------:|
| Bull | 70% | 20% | 10% |
| Bear | 40% | 30% | 30% |
| Crisis | 20% | 40% | 40% |

Transaction costs were included during rebalancing.

---

## Benchmarks

The strategy was compared against:

- Equal Weight Portfolio
- 60/40 Portfolio

---

## Performance Metrics

The following metrics were calculated:

- Sharpe Ratio
- Sortino Ratio
- Calmar Ratio
- Maximum Drawdown
- Average Turnover

---

## Libraries Used

- Python
- pandas
- numpy
- matplotlib
- yfinance
- hmmlearn
- scikit-learn
- cvxpy

---

## Repository Structure

```
RegimeShift.ipynb
README.md
```

---

## How to Run

1. Clone the repository.
2. Open `RegimeShift.ipynb` in Google Colab or Jupyter Notebook.
3. Install the required libraries.
4. Run all cells from top to bottom.
5. The notebook downloads data, detects regimes, performs backtesting and displays the final results.

---

## Author

**Yash Kashyap**

Indian Institute of Technology Bombay
