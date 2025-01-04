# US Treasury Yield Curve Analyzer

A Python tool for analyzing, visualizing, and stress testing US Treasury yield curves using data from the Federal Reserve Economic Data (FRED).

## Features

- Fetch historical Treasury yield data across multiple maturities (1M to 30Y)
- Calculate and visualize yield curves at specific dates
- Generate historical yield visualizations
- Calculate forward rates (1y1y, 2y1y, 5y5y)
- Perform spread analysis (2s10s, 3m10y, 5s30s)
- Conduct stress testing based on historical moves
- Generate interactive plots using Plotly

## Installation

### Prerequisites

- Python 3.7+
- pip package manager

### Required Packages

pip install pandas pandas-datareader numpy plotly typing

## Usage

### Basic Usage

from datetime import datetime
from us_yield_curve_analyzer import USYieldCurveAnalyzer

# Initialize the analyzer
analyzer = USYieldCurveAnalyzer()

# Fetch yield data starting from 2015
yields_data = analyzer.fetch_yields(start_date=datetime(2015, 1, 1))

# Plot current yield curve
yield_curve = analyzer.plot_yield_curve()
yield_curve.show()

# Generate historical yield visualization
historical = analyzer.plot_historical_yields(start_year=2015)
historical.show()

### Advanced Features

#### Calculate Forward Rates

# Get forward rates
forward_rates = analyzer.calculate_forward_rates()
print(forward_rates.tail(1))

# Plot forward rates
forward_plot = analyzer.plot_forward_rates()
forward_plot.show()

#### Stress Testing

# Perform stress testing
stress_results = analyzer.stress_test_yields()
print(stress_results)

# Visualize stress test results
stress_plot = analyzer.plot_stress_test_results(stress_results)
stress_plot.show()

## Class Methods

### Core Methods

- `fetch_yields(start_date)`: Fetches Treasury yield data from FRED
- `plot_yield_curve(date)`: Plots the yield curve for a specific date
- `plot_historical_yields(start_year)`: Visualizes historical yields across different maturities

### Analysis Methods

- `calculate_forward_rate(start_tenor, end_tenor)`: Calculates forward rates between two tenors
- `calculate_forward_rates()`: Calculates common forward rate combinations (1y1y, 2y1y, 5y5y)
- `calculate_spreads()`: Computes yield curve spreads (2s10s, 3m10y, 5s30s)

### Stress Testing Methods

- `calculate_historical_moves(lookback_days)`: Analyzes historical yield movements
- `stress_test_yields(lookback_days)`: Performs stress testing based on historical scenarios
- `plot_stress_test_results(stress_results)`: Visualizes stress test outcomes

## Data Structure

The analyzer uses the following Treasury maturities:
- 1-month (1M)
- 3-month (3M)
- 6-month (6M)
- 1-year (1Y)
- 2-year (2Y)
- 3-year (3Y)
- 5-year (5Y)
- 7-year (7Y)
- 10-year (10Y)
- 20-year (20Y)
- 30-year (30Y)

## Error Handling

The tool implements comprehensive error handling and logging:
- Failed data fetches are logged with detailed error messages
- Invalid tenor specifications raise ValueError
- Missing data scenarios are handled gracefully

## Visualization

All visualizations are created using Plotly, providing:
- Interactive plots
- Hover information
- Customizable layouts
- Export capabilities

## Logging

The tool uses Python's built-in logging module with:
- INFO level for successful operations
- ERROR level for failed operations
- Detailed error messages for debugging

## Contributing

Feel free to submit issues and enhancement requests!
