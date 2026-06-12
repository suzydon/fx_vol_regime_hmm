# FX Volatility Regime Detection — Hidden Markov Model

Unsupervised detection of volatility regimes in EUR/USD using a Gaussian Hidden
Markov Model, on real data.

## Method
- Daily EUR/USD from Yahoo Finance (2004-present).
- Features: daily log returns and short-window realized volatility.
- A 3-state Gaussian HMM learns hidden states, labelled Low / Medium / High
  volatility by their realized-vol level.
- Reports time spent in each regime, regime-dependent return and volatility,
  expected regime duration, and a regime-coloured price chart.

## Running it
```bash
pip install yfinance hmmlearn scikit-learn pandas numpy matplotlib
```
Run the notebook top to bottom. Saves `fx_vol_regime_results.png`.

## Results
*Run the notebook and paste the regime table + chart here.*

## Limitations
- Number of regimes (3) is a modelling choice; 2 or 4 states partition differently.
- A Gaussian HMM understates fat tails in returns.
- Regimes are inferred over the full sample; a live detector would re-fit on a
  rolling basis to avoid look-ahead in the labels.
