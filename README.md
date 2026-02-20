# Data Analysis with Python

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Pandas](https://img.shields.io/badge/pandas-1.3+-green.svg)](https://pandas.pydata.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> Comprehensive tax data analysis project demonstrating end-to-end data analysis workflow using Python.

## Overview

This project demonstrates a complete data analysis pipeline on synthetic tax data, covering:
- Data generation and simulation
- Data cleaning and preprocessing
- Exploratory Data Analysis (EDA)
- Statistical analysis and tax calculations
- Data visualization

## Project Structure

```
Data-Analysis-with-Python/
├── README.md                                    # This file
├── requirements.txt                             # Dependencies
├── notebooks/
│   ├── 01_tax_data_generation.ipynb            # Synthetic data creation
│   └── 02_tax_analysis_and_visualization.ipynb # Full analysis workflow
├── src/
│   ├── __init__.py
│   ├── data_generator.py                        # Tax data simulation
│   ├── tax_calculator.py                        # Tax computation logic
│   └── visualizations.py                        # Plotting utilities
└── data/
    └── synthetic_tax_data.csv                   # Generated dataset
```

## Datasets

### Project 1: Tax Data Analysis
- **Records**: 1,000 synthetic tax records
- **Features**:
  - `income`: Annual income (USD)
  - `deductions`: Tax deductions (USD)
  - `tax_rate`: Categorical tax bracket (10%-35%)
  - `filing_status`: Single, Married Filing Jointly, Head of Household, Married Filing Separately

## Key Techniques

| Technique | Description |
|-----------|-------------|
| **Synthetic Data Generation** | Using NumPy to simulate realistic tax scenarios |
| **Data Cleaning** | Handling missing values, outliers, data type conversions |
| **EDA** | Distribution analysis, correlation studies |
| **Feature Engineering** | Tax liability calculations, effective rate computation |
| **Visualization** | Matplotlib/Seaborn for insights communication |

## Installation

```bash
# Clone the repository
git clone https://github.com/MusaBrown/Data-Analysis-with-Python.git
cd Data-Analysis-with-Python

# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

## Dependencies

```
numpy>=1.20.0
pandas>=1.3.0
matplotlib>=3.4.0
seaborn>=0.11.0
jupyter>=1.0.0
```

## Usage

### Running the Notebooks

```bash
jupyter notebook notebooks/
```

### Quick Start

```python
import pandas as pd
import numpy as np
from src.tax_calculator import calculate_tax_liability

# Load synthetic tax data
df = pd.read_csv('data/synthetic_tax_data.csv')

# Calculate tax liability
df['tax_liability'] = df.apply(
    lambda row: calculate_tax_liability(row['income'], row['deductions'], row['tax_rate']),
    axis=1
)

# Summary statistics
print(df.groupby('filing_status')['tax_liability'].mean())
```

## Analysis Workflow

### 1. Data Generation
- Simulated 1,000 tax records with realistic distributions
- Income: Normal distribution (μ=$60,000, σ=$20,000)
- Deductions: 5-30% of income
- Tax rates: Categorical brackets (10%, 15%, 20%, 25%, 30%, 35%)

### 2. Data Inspection
- Structure validation
- Missing value detection
- Data type verification
- Statistical summaries

### 3. Exploratory Data Analysis
- Income distribution by filing status
- Deduction patterns analysis
- Tax rate distribution
- Correlation between variables

### 4. Tax Calculations
- Gross tax liability computation
- Effective tax rate analysis
- Net tax payable after deductions
- Comparative analysis across filing statuses

### 5. Visualization
- Distribution plots (histograms, KDE)
- Box plots for outlier detection
- Scatter plots for relationship analysis
- Bar charts for categorical comparisons

## Key Insights

1. **Income Distribution**: Right-skewed distribution with most earners in $40k-$80k range
2. **Filing Status Impact**: Married Filing Jointly shows highest average deductions
3. **Tax Rate Correlation**: Higher incomes correlate with higher tax brackets
4. **Deduction Patterns**: Standard deduction vs. itemized analysis

## Sample Visualizations

*Generated in notebooks:*
- Income distribution by filing status
- Tax liability vs. income scatter plot
- Effective tax rate comparison
- Deduction amount distributions

## Skills Demonstrated

- **Python Programming**: NumPy, Pandas for data manipulation
- **Data Cleaning**: Handling real-world data quality issues
- **Statistical Analysis**: Descriptive statistics, correlation analysis
- **Data Visualization**: Clear, informative plots with Matplotlib/Seaborn
- **Domain Knowledge**: Understanding of tax structures and calculations

## Future Enhancements

- [ ] SQL integration for database operations
- [ ] DAX calculations for Power BI integration
- [ ] Time-series analysis for multi-year tax trends
- [ ] Predictive modeling for tax liability estimation
- [ ] Interactive dashboards with Plotly/Dash

## Learning Outcomes

This project demonstrates proficiency in:
- End-to-end data analysis workflow
- Python data science stack (NumPy, Pandas, Matplotlib, Seaborn)
- Business domain understanding (tax regulations)
- Technical documentation and code organization

## License

MIT License — see [LICENSE](LICENSE) for details.

## Author

Brown — [@MusaBrown](https://github.com/MusaBrown)

---

*Project completed as part of data science skill development.*
