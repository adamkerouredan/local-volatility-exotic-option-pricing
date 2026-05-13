# Local Volatility Modelling & Exotic Option Pricing

This project implements a quantitative framework for exotic option pricing under Dupire local volatility.

The notebook connects several components of an equity derivatives workflow:

- Black-Scholes pricing and implied volatility inversion;
- SVI-style implied volatility surface construction;
- market-data-like option quote simulation;
- quote cleaning and implied volatility reconstruction;
- Dupire local volatility extraction;
- Monte Carlo pricing of down-and-out barrier options;
- Greeks estimation by bump-and-reprice;
- risk monitoring and P&L diagnostics.

## Main Components

### 1. Implied Volatility Surface

A synthetic equity-style implied volatility surface is generated using SVI-inspired parameters. The surface captures a negative skew and a realistic term structure.

### 2. Market Data Simulation

The project simulates an option chain with strikes, maturities, OTM option selection, bid/ask spreads, noisy mid prices and volume-based liquidity.

The simulated quotes are cleaned using basic market-data filters before reconstructing implied volatility from mid prices.

### 3. Dupire Local Volatility

Dupire's formula is applied through finite differences on the option price surface to extract a local volatility surface.

### 4. Barrier Option Pricing

The framework prices down-and-out calls under both Black-Scholes flat volatility and Dupire local volatility.

The comparison highlights model risk for path-dependent products.

### 5. Risk Monitoring & P&L Diagnostics

The notebook includes desk-oriented diagnostics:

- model-risk comparison;
- spot stress testing;
- barrier stress testing;
- knock-out probability monitoring;
- full revaluation P&L;
- Delta-Gamma P&L attribution.

## Key Result

Two models consistent with the same vanilla option information can produce different prices for barrier options.

This is because barrier options are path-dependent: their value depends on the full trajectory of the underlying, not only on the terminal distribution.

## Repository Structure

- notebooks/ : main research notebook
- reports/ : written report
- figures/ : exported figures
- data/ : placeholders for raw, processed and simulated data
- docs/ : additional project documentation

## How to Run

Install the dependencies:

    pip install -r requirements.txt

Then open and run:

    notebooks/local_volatility_exotic_option_pricing.ipynb

## Limitations

The current version uses synthetic SVI parameters and simulated option quotes. Future improvements include calibration on real option market data, stricter no-arbitrage controls, variance reduction, barrier monitoring correction and dynamic hedging backtests.

## Disclaimer

This project is for educational and research purposes only. It is not a production pricing or risk engine.
