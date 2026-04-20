# Electricity Generation and Demand Analysis for Ireland and Northern Ireland (2024)

## Project Overview

This project provides a comprehensive analysis of electricity generation and demand patterns for Ireland (IE) and Northern Ireland (NI) throughout 2024. Using 15-minute interval data, the analysis examines seasonal trends, renewable energy integration, grid balance, and operational patterns across both regions.

## Dataset

- **Source**: System_Data_Qtr_Hourly_2024.xlsx
- **Time Resolution**: 15-minute intervals
- **Regions**: Ireland (IE) and Northern Ireland (NI)
- **Coverage**: Full year 2024

### Data Columns
- **DateTime**: Timestamp of measurement
- **NI/IE Generation**: Total electricity generation (MW)
- **NI/IE Demand**: Electricity demand (MW)
- **NI/IE Wind Generation**: Wind-generated electricity (MW)
- **NI/IE Solar Generation**: Solar-generated electricity (MW)

## Analysis Questions

This notebook addresses 10 key analysis questions:

1. **Data Loading & Quality Checks** - Validate data integrity, check for missing values and time continuity
2. **Monthly Statistics** - Compute mean, max, min values for demand and renewable generation by month
3. **Daily & Weekly Averages** - Time series analysis of demand vs generation
4. **Autocorrelation Analysis** - Temporal dependencies in wind and solar generation (up to 10 days)
5. **Monthly Bar Charts** - Visual comparison of seasonal patterns
6. **Daily Renewable Profiles** - Hourly generation patterns for solar and wind
7. **Weekly Demand Patterns** - Day-of-week electricity consumption analysis
8. **Hourly Demand Profiles** - Detailed demand patterns by day of week
9. **Statistical Hypothesis Testing** - Weekend vs weekday differences (t-tests)
10. **Wind Penetration Rates** - Distribution analysis of wind generation as % of demand

## Key Findings

### Seasonal Patterns
- **Winter peaks** (Jan-Feb): Highest electricity consumption due to heating demands
- **Summer lows** (Jun-Aug): Lowest demand periods
- **Regional Scale**: Ireland operates at approximately 4x the capacity of Northern Ireland
- Both regions maintain consistent seasonal patterns despite scale differences

### Renewable Integration
- **Wind Generation**: Strong seasonal variation with winter peaks; shows multi-day persistence patterns
- **Solar Generation**: Predictable diurnal cycle (bell-shaped, peaking at midday)
- **Complementarity**: Wind provides overnight generation; solar covers daytime demand peaks
- **Wind Penetration**: 
  - Northern Ireland: Averages >50%, capable of exceeding 150%
  - Ireland: Typically 20-40% penetration

### Grid Operations
- Generation reliably tracks demand across all seasons
- Clear weekday-weekend demand difference (~130 MW for NI, ~550 MW for IE)
- Strong evidence of effective grid balancing and management
- Predictable patterns enable reliable load forecasting

### Demand Behavior
- **Weekday peaks**: 6-9 AM and 6-8 PM
- **Weekend patterns**: Later morning peaks, more variable daytime consumption
- **Statistical significance**: p < 0.000001 for weekday-weekend demand differences
- Solar generation unaffected by day-of-week (p > 0.05)

## Technical Stack

- **Python 3.x**
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computing
- **Matplotlib & Seaborn**: Data visualization
- **SciPy**: Statistical tests
- **Statsmodels**: Time series analysis (ACF)

## Getting Started

### Prerequisites
- Python 3.7+
- Jupyter Notebook or VS Code with Jupyter extension

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/electricity-generation-and-demand-analysis.git
cd electricity-generation-and-demand-analysis
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Ensure the data file is in the project root:
```
System_Data_Qtr_Hourly_2024.xlsx
```

4. Open and run the notebook:
```bash
jupyter notebook electricity\ generation\ and\ demand\ analysis.ipynb
```

## File Structure

```
.
├── README.md                                           # Project documentation
├── requirements.txt                                    # Python dependencies
├── .gitignore                                          # Git exclusions
├── electricity generation and demand analysis.ipynb    # Main analysis notebook
└── System_Data_Qtr_Hourly_2024.xlsx                   # Data file
```

## Methodology

### Data Quality Assurance
- Validation of temporal continuity (15-minute intervals)
- Detection of missing values and negative values
- DateTime parsing and feature engineering (Hour, Day, Month, Week, DayOfWeek)

### Analysis Techniques
- **Descriptive Statistics**: Mean, median, max, min by temporal periods
- **Time Series Analysis**: Autocorrelation function (ACF) for lag analysis
- **Statistical Testing**: Independent samples t-tests (Welch's)
- **Visualization**: Multiple chart types (line, bar, histogram)

### Key Metrics
- **Wind Penetration Rate**: (Wind Generation / Demand) × 100%
- **Seasonal Variations**: Percentage differences between peaks and troughs
- **Demand-Generation Alignment**: Correlation and tracking analysis

## Usage

The notebook is designed to be run sequentially. Each cell is self-contained but builds on data processed in previous cells.

**To run the entire analysis:**
1. Execute Cell 1 to load and prepare data
2. Run cells 2-10 for each analysis question
3. Visualizations and statistical outputs display directly

## Results & Visualizations

The notebook generates multiple visualizations:
- Daily and weekly time series plots
- Autocorrelation function plots (4 subplots)
- Monthly bar charts
- Hourly generation profiles
- Day-of-week demand patterns
- Wind penetration rate distributions

## License

This project is for educational purposes.

## Data Sources

- **Ireland & Northern Ireland Electricity System Data**
- System: Quarterly/Hourly Resolution
- Year: 2024
- Data format: Excel (.xlsx)

---
