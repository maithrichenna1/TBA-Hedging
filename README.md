# TBA-Hedging
This project will evaluate the effectiveness of TBA hedging against MSR prepayment risks using historical data. We'll analyze hedge ratios, compare pool performance with TBA hedges, and generate risk-adjusted returns.

# TBA Hedging Model

## Project Overview
This project evaluates the effectiveness of TBA hedging against MSR (Mortgage Servicing Rights) prepayment risks. The model calculates hedge ratios, analyzes risk-adjusted returns, and backtests different hedging strategies using historical data.

## Repository Structure
```
TBA-Hedging-Model/
│── data/                  # Sample datasets (historical TBA & MSR data)
│── notebooks/             # Jupyter Notebooks for analysis
│── scripts/               # Python scripts for automation
│── models/                # Machine learning/statistical models
│── reports/               # Graphs, risk metrics, and analysis reports
│── README.md              # Project documentation
│── requirements.txt       # Dependencies
│── .gitignore             # Ignore unnecessary files
```

## Installation
```bash
pip install -r requirements.txt
```

## Usage
Run the hedge ratio calculation script:
```bash
python scripts/hedge_ratio_calculator.py
```

## Sample Code (scripts/hedge_ratio_calculator.py)
```python
import pandas as pd
import statsmodels.api as sm

def load_data(file_path):
    """Load historical TBA and MSR data from CSV."""
    return pd.read_csv(file_path)

def calculate_hedge_ratio(data):
    """Calculate hedge ratio using linear regression."""
    X = data['TBA Returns']
    y = data['MSR Returns']
    X = sm.add_constant(X)  # Add intercept
    model = sm.OLS(y, X).fit()
    return model.params

if __name__ == "__main__":
    df = load_data("data/tba_msr_returns.csv")
    hedge_ratio = calculate_hedge_ratio(df)
    print("Optimal Hedge Ratio:", hedge_ratio)
```

## Next Steps
- Expand dataset with real historical TBA and MSR data.
- Implement risk-adjusted return analysis.
- Add backtesting functionality for different hedge strategies.

---
This is the initial framework. Let me know if you need modifications or additional features!

