# Heston Stochastic Volatility Model with Mean Reversion

This repository contains a Python implementation of the Heston stochastic volatility model for stock price simulation, enhanced with a custom mean-reversion component pulling prices toward their 52-week moving average. It also includes backtesting against historical data and comparison with the Black-Scholes model.

## Features

- Download and preprocess stock data using Yahoo Finance (`yfinance`)
- Simulate multiple stock price paths using the Heston model with stochastic variance
- Custom mean-reversion strategy toward 52-week average price for more realistic price dynamics
- Backtesting framework comparing model outputs against historical price data
- Black-Scholes model simulation for baseline comparison
- Visualization of simulated paths, percentile bands, and final price distributions
- Performance metrics: RMSE and Median Absolute Error (MedAE)

## Usage
pip install yfinance numpy matplotlib


abhinav00345@gmail.com 
