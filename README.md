# RegimeShift: Market Regime Detection and Dynamic Portfolio Allocation

## Overview

RegimeShift is a quantitative finance project that uses a Hidden Markov Model (HMM) to identify hidden market regimes and dynamically adjust portfolio allocations across equities, gold, and bonds. The project aims to improve portfolio performance by adapting investment strategies to changing market conditions.

## Project Objectives

- Detect hidden market regimes using a Gaussian Hidden Markov Model.
- Classify market conditions into Bull, Bear, and Crisis regimes.
- Perform walk-forward validation to reduce look-ahead bias.
- Dynamically allocate portfolio weights based on the detected regime.
- Compare the strategy with traditional benchmark portfolios.

## Dataset

Historical daily market data was obtained using the `yfinance` library.

Assets used:
- NIFTY 50 (`^NSEI`)
- Gold ETF (`GOLDBEES.NS`)
- Bond ETF (`SETFNIFBK.NS`)
- India VIX (`^INDIAVIX`)

## Feature Engineering

The following features were extracted for regime detection:

- Daily Returns
- 5-Day Momentum
- 20-Day Momentum
- 20-Day Rolling Volatility
- India VIX

These features capture market trends, volatility, and investor sentiment.

## Methodology

1. Download historical market data.
2. Preprocess the data and generate market features.
3. Standardize the feature set.
4. Train a 3-state Gaussian Hidden Markov Model.
5. Detect Bull, Bear, and Crisis market regimes.
6. Perform walk-forward validation.
7. Allocate portfolio weights dynamically based on the detected regime.
8. Incorporate transaction costs during portfolio rebalancing.
9. Compare the strategy against Equal Weight and 60/40 benchmark portfolios.

## Portfolio Allocation

| Market Regime | NIFTY | Gold | Bonds |
|---------------|------:|------:|------:|
| Bull | 70% | 20% | 10% |
| Bear | 40% | 30% | 30% |
| Crisis | 20% | 40% | 40% |

## Performance Evaluation

The strategy is evaluated using:

- Sharpe Ratio
- Sortino Ratio
- Calmar Ratio
- Maximum Drawdown
- Average Portfolio Turnover

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- yfinance
- hmmlearn
- scikit-learn
- CVXPY

## Repository Structure

```
RegimeShift/
│── RegimeShift.ipynb
│── README.md
│── requirements.txt
```

## Installation

Install the required libraries using:

```bash
pip install -r requirements.txt
```

## Running the Project

1. Clone this repository.
2. Open `RegimeShift.ipynb` in Google Colab or Jupyter Notebook.
3. Run all notebook cells sequentially.
4. The notebook will:
   - Download market data
   - Generate features
   - Detect market regimes
   - Perform portfolio allocation
   - Backtest the strategy
   - Display performance metrics and visualizations

## Results

The project demonstrates how Hidden Markov Models can identify different market regimes and enable dynamic asset allocation. Strategy performance is compared with Equal Weight and 60/40 benchmark portfolios using standard risk-adjusted performance metrics.

## Author

**Yash Kashyap**  
Department of Chemical Engineering  
Indian Institute of Technology Bombay
