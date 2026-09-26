# ASML Monte Carlo Simulation

A Python project that uses historical ASML share-price data to simulate possible three-year outcomes for a $10,000 investment.

## Overview

This project downloads five years of daily ASML market data, calculates historical returns and volatility, and runs 10,000 Monte Carlo simulations over a three-year period.

The aim is to show how a wide range of outcomes can result when an investment is exposed to share-price volatility. It is not intended to predict ASML's future share price.

## Question

What could happen to a $10,000 investment in ASML over the next three years if future daily price movements broadly follow the historical return and volatility observed in the previous five years?

## Method

1. Download five years of daily ASML share-price data using `yfinance`.
2. Calculate daily percentage returns from the adjusted closing-price series.
3. Estimate the average daily return and daily volatility from the historical sample.
4. Use geometric Brownian motion to simulate 10,000 possible price paths over 756 trading days (three years).
5. Convert each simulated price path into the value of a $10,000 investment.
6. Summarise the final values using the median, 5th percentile, 95th percentile, and probability of loss.

## Project structure

```text
asml-monte-carlo-simulation/
├── README.md
├── requirements.txt
├── simulation_summary.csv
├── notebooks/
│   └── asml_monte_carlo_simulation.ipynb
└── figures/
    ├── simulated_price_paths.png
    └── final_investment_value_distribution.png
```

## Charts

### Simulated price paths

![Simulated ASML price paths](figures/simulated_price_paths.png)

### Distribution of final investment values

![Distribution of simulated final investment values](figures/final_investment_value_distribution.png)

## Results

The notebook creates a table called `simulation_summary.csv` containing the exact results from the simulation run. It includes:

- Starting ASML share price
- Historical annualised return and volatility
- Median and mean final portfolio value
- 5th and 95th percentile final values
- Probability of ending below the initial $10,000 investment

The results will change if the historical period, random seed, or model assumptions are changed.

## How to run

1. Open `notebooks/asml_monte_carlo_simulation.ipynb` in Google Colab or Jupyter Notebook.
2. Install the required packages:

```bash
pip install -r requirements.txt
```

3. Run the cells in order.
4. The notebook downloads historical ASML data and generates the figures and results summary.

## Limitations

- The model uses historical price data, which does not guarantee future results.
- It assumes that historical return and volatility are useful estimates for the next three years.
- It does not account for earnings announcements, valuation changes, macroeconomic shocks, semiconductor cycles, geopolitical events, or other company-specific developments.
- A Monte Carlo simulation produces hypothetical scenarios, not a price target or investment recommendation.

## Tools used

- Python
- pandas
- NumPy
- matplotlib
- yfinance
- Google Colab
