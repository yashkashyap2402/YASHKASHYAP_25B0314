# RegimeShift

## Objective
Detect market regimes (Bull, Bear, Crisis) using a Hidden Markov Model (HMM) and allocate a portfolio across equity, gold and bonds.

## Tools Used
- Python
- Google Colab
- yfinance
- hmmlearn
- cvxpy
- pandas
- numpy
- matplotlib

## Methodology
1. Download historical market data.
2. Calculate returns and volatility.
3. Train a 3-state Gaussian Hidden Markov Model.
4. Identify market regimes.
5. Allocate portfolio weights based on detected regime.
6. Backtest the strategy.
7. Compare performance with benchmark portfolios.

## Assets
- NIFTY 50
- Gold ETF
- Bond ETF

## Results
- Equity curve
- Sharpe Ratio
- Maximum Drawdown
- Portfolio returns

## Author
Yash Kashyap
