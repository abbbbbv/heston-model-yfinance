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

Heston Model Overview:
----------------------
The Heston model introduces stochastic volatility into the standard Black-Scholes framework.

Core Dynamics (S = stock price, V = variance):
    dS_t = μ * S_t * dt + sqrt(V_t) * S_t * dW1_t
    dV_t = κ(θ - V_t) * dt + σ * sqrt(V_t) * dW2_t

Discretization:
    S_{t+1} = S_t + μ * S_t * dt + sqrt(V_t) * S_t * sqrt(dt) * Z1
    V_{t+1} = V_t + κ(θ - V_t) * dt + σ * sqrt(V_t) * sqrt(dt) * Z2

Where:
    - Z1 and Z2 are standard normal variables with correlation ρ
    - dW2_t = ρ * dW1_t + sqrt(1 - ρ²) * dZ_t (correlated Brownian motions)

Custom Modification:
---
To improve realism, a **mean reversion strategy toward the 52-week average price** is added to the S_t update step.
This dynamic pulls the simulated stock prices back toward a long-term average, scaled by:
    - Deviation from the 52-week average
    - Decay over time
    - Estimated return magnitude (μ)
    - Stronger influence in early steps due to possible skew of extreme returns
This approach aims to capture the tendency of stock prices to revert to their historical averages, enhancing the model's realism.


## Usage
pip install yfinance numpy matplotlib


abhinav00345@gmail.com 
