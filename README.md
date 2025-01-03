# US Treasury Yield Curve Analysis

A Python package for analyzing US Treasury yield curves, calculating forward rates, and performing stress testing. This tool provides functionality to fetch real-time Treasury data, visualize yield curves, calculate forward rates, and conduct stress testing scenarios.

## Features

- Fetch real-time US Treasury yield data from FRED
- Plot interactive yield curves using Plotly
- Calculate and visualize forward rates (1y1y, 2y1y, 5y5y)
- Perform stress testing with historical scenarios
- Calculate and analyze yield curve spreads (2s10s, 3m10y, 5s30s)
- Generate historical yield visualizations

## Installation

# Clone the repository
git clone https://github.com/yourusername/treasury-yield-analysis.git
cd treasury-yield-analysis

# Install dependencies
pip install -r requirements.txt

## Quick Start

from treasury_analysis.analyzer import USYieldCurveAnalyzer
from datetime import datetime

# Initialize the analyzer
analyzer = USYieldCurveAnalyzer()

# Fetch yield data starting from 2015
yields = analyzer.fetch_yields(start_date=datetime(2015, 1, 1))

# Plot current yield curve
yield_curve = analyzer.plot_yield_curve()
yield_curve.show()

# Calculate forward rates
forwards = analyzer.calculate_forward_rates()
print("\nLatest Forward Rates:")
print(forwards.tail(1))

# Run stress tests
stress_results = analyzer.stress_test_yields()
print("\nStress Test Results:")
print(stress_results)

## Example Outputs

The package generates interactive Plotly visualizations including:
- Current yield curve shape
- Historical yield movements
- Forward rate trends
- Stress test scenario impacts

## Dependencies

- pandas >= 1.3.0
- pandas-datareader >= 0.10.0
- numpy >= 1.20.0
- plotly >= 5.3.0

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
