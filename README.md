# RegimeShift

A quantitative finance project that uses a Hidden Markov Model (HMM) to detect hidden market regimes and dynamically allocate a portfolio across equities, gold, and bonds.

## Project Objective

The objective of this project is to identify different market regimes (Bull, Bear, and Crisis) and adjust portfolio allocations based on the detected regime. The strategy is evaluated using walk-forward validation and compared against traditional benchmark portfolios.

## Dataset

Historical daily market data was collected using Yahoo Finance (`yfinance`).

Assets used:
- NIFTY 50 (`^NSEI`)
- Gold ETF (`GOLDBEES.NS`)
- Bond ETF (`SETFNIFBK.NS`)
- India VIX (`^INDIAVIX`)

## Feature Engineering

The following features were used for regime detection:
- Daily Returns
- 5-Day Momentum
- 20-Day Momentum
- 20-Day Rolling Volatility
- India VIX

## Methodology

- Download historical market data
- Preprocess and engineer market features
- Train a 3-state Gaussian Hidden Markov Model
- Detect Bull, Bear, and Crisis market regimes
- Perform walk-forward validation
- Dynamically allocate portfolio weights based on the detected regime
- Include transaction costs during portfolio rebalancing
- Compare performance with Equal Weight and 60/40 benchmark portfolios

## Performance Metrics

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
├── RegimeShift.ipynb
├── README.md
└── requirements.txt
```

## How to Run

1. Clone this repository.
2. Install the required dependencies using:

```bash
pip install -r requirements.txt
```

3. Open `RegimeShift.ipynb` in Jupyter Notebook or Google Colab.
4. Run all cells sequentially to reproduce the analysis and results.

## Author

**Yash Kashyap**  
Department of Chemical Engineering  
Indian Institute of Technology Bombay
