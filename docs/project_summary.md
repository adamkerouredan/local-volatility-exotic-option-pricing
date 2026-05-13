# Project Summary

This project studies exotic option pricing under Dupire local volatility.

The workflow starts from an implied volatility surface, simulates a market-like option chain, reconstructs implied volatility from cleaned mid prices, extracts local volatility, prices down-and-out calls by Monte Carlo simulation and adds a risk monitoring layer.

The main result is that local volatility and Black-Scholes flat volatility may both be consistent with vanilla option prices, while still producing different prices for path-dependent derivatives.

The project includes model-risk comparison, spot stress, barrier stress, knock-out probability monitoring and Delta-Gamma P&L attribution.
