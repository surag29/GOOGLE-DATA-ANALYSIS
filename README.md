# Google Data Analysis

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Data Analysis](https://img.shields.io/badge/Analysis-Google%20Trends-informational)](https://trends.google.com/)

## Overview

This repository contains a comprehensive data analysis project focused on extracting, visualizing, and interpreting Google Trends data. The project leverages the `pytrends` library to collect search trend data and uses Python's data visualization ecosystem to generate insightful charts and geographical representations.

## Project Description

Google Trends analysis is a powerful tool for understanding search behavior patterns across the globe. This project analyzes trending search keywords over time, identifying:

- **Geographic Distribution**: Countries and regions with the highest search interest
- **Temporal Patterns**: How search interest fluctuates over a 12-month period
- **Keyword Comparisons**: Comparative analysis of multiple related keywords
- **Search Interest Metrics**: Relative search volume indexed from 0-100

## Key Features

✨ **Multiple Analysis Dimensions**
- Single keyword trend analysis
- Multi-keyword comparison across time
- Country-wise interest distribution
- World map visualization of search trends
- Time-series trend tracking (12-month historical data)

📊 **Visualization Capabilities**
- Bar charts for country-wise search rankings
- Interactive choropleth world maps
- Time-series line plots with trend markers
- Multi-line comparisons for keyword analysis

⚙️ **Technology Stack**
- **Data Collection**: PyTrends (unofficial Google Trends API)
- **Data Processing**: Pandas, NumPy
- **Visualization**: Matplotlib, Seaborn, Plotly Express
- **Environment**: Jupyter Notebook

## Project Structure

```
GOOGLE-DATA-ANALYSIS/
├── google-search-analysis.ipynb    # Main analysis notebook
├── anaconda_projects/
│   └── db/                         # Database configuration files
├── .ipynb_checkpoints/             # Jupyter notebook checkpoints
└── README.md                       # This file
```

## Installation & Setup

### Prerequisites

- Python 3.8 or higher
- Jupyter Notebook or JupyterLab
- pip (Python package manager)

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/surag29/GOOGLE-DATA-ANALYSIS.git
   cd GOOGLE-DATA-ANALYSIS
   ```

2. **Create a virtual environment (recommended)**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install required packages**
   ```bash
   pip install -r requirements.txt
   ```
   
   Or manually install:
   ```bash
   pip install pytrends numpy pandas matplotlib seaborn plotly jupyter
   ```

4. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

## Usage Guide

### Basic Workflow

1. **Initialize PyTrends**
   ```python
   from pytrends.request import TrendReq
   
   pytrends = TrendReq(hl='en-US', tz=360)
   ```

2. **Define Keywords**
   ```python
   keyword = ["cloud computing"]
   # For multiple keywords:
   kw_list = ["cloud computing", "data science", "machine learning"]
   ```

3. **Build Payload**
   ```python
   pytrends.build_payload(
       keyword,
       cat=0,
       timeframe='today 12-m',  # Last 12 months
       geo='',  # Empty for worldwide
       gprop=''
   )
   ```

4. **Retrieve and Analyze Data**
   ```python
   # Geographic distribution
   region_data = pytrends.interest_by_region()
   
   # Time-series data
   time_df = pytrends.interest_over_time()
   ```

### Analysis Sections in Notebook

#### 1. **Country-wise Interests**
   - Retrieves search interest by country
   - Ranks top 15 countries by search volume
   - Generates horizontal bar charts for comparison

#### 2. **World Map Visualization**
   - Creates interactive choropleth map
   - Uses geographic color mapping based on interest levels
   - Enables drill-down exploration of global trends

#### 3. **Time-wise Interest**
   - Tracks interest evolution over 12 months
   - Plots time-series data with date-based x-axis
   - Identifies peak interest periods and trends

#### 4. **Multiple Keywords Comparison**
   - Compares up to 5 keywords simultaneously
   - Overlays multiple trend lines
   - Helps identify which keywords are gaining/losing popularity

## Dependencies

| Package | Version | Purpose |
|---------|---------|----------|
| pytrends | Latest | Google Trends data collection |
| pandas | ≥1.3.0 | Data manipulation and analysis |
| numpy | ≥1.21.0 | Numerical computations |
| matplotlib | ≥3.4.0 | Static visualization |
| seaborn | ≥0.11.0 | Statistical data visualization |
| plotly | ≥5.0.0 | Interactive visualizations |
| jupyter | ≥1.0.0 | Notebook environment |

## Results & Insights

This project generates:

- **Regional Rankings**: Identification of countries with highest search interest
- **Trend Patterns**: Seasonal or cyclical patterns in search behavior
- **Keyword Evolution**: How different terms gain/lose prominence over time
- **Comparative Metrics**: Relative popularity of competing keywords or topics

### Example Analyses

- Track the popularity of "cloud computing" across different regions
- Compare search interest for "data science", "machine learning", and "artificial intelligence"
- Identify emerging technology trends in different countries
- Monitor keyword relevance for content marketing strategies

## Limitations & Considerations

⚠️ **Important Notes**

1. **Rate Limiting**: PyTrends may throttle requests if too many are made in quick succession
2. **Index Scale**: Results are indexed 0-100, not absolute search volumes
3. **Data Freshness**: Google Trends data updates with a 48-72 hour delay
4. **API Status**: PyTrends is an unofficial API and may break with Google Trends updates
5. **Geographic Variations**: Results may vary based on selected timeframe and region

## Best Practices

✅ **Recommended Approaches**

- Use descriptive keyword terms rather than single letters
- Limit to 5 keywords per comparison for clarity
- Implement delays between requests to avoid rate limiting
- Validate findings with additional data sources
- Document assumptions and timeframe for reproducibility

## Future Enhancements

🚀 **Potential Improvements**

- Integration with other data sources (Twitter trends, news analytics)
- Sentiment analysis of trending topics
- Automated report generation and email delivery
- Real-time monitoring dashboard with alerts
- Predictive modeling for future trend forecasts
- Integration with SQL/NoSQL databases for historical tracking

## Contributing

Contributions are welcome! Please feel free to:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -m 'Add new analysis feature'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Author

**Suraj** ([surag29](https://github.com/surag29))

For questions or suggestions, please open an issue on the repository.

## References & Resources

- [PyTrends Documentation](https://github.com/GeneralMills/pytrends)
- [Google Trends](https://trends.google.com/)
- [Plotly Documentation](https://plotly.com/python/)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Data Analysis Best Practices](https://www.oreilly.com/library/view/python-for-data-analysis/)

## Acknowledgments

This project was developed as part of learning data analysis and visualization techniques using Python. Special thanks to the PyTrends community for maintaining the unofficial Google Trends API.

---

**Last Updated**: December 2025  
**Status**: Active Development
