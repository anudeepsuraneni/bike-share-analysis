# Bike-share Analysis

A comprehensive analysis of bike-share data to understand user behavior and improve business strategies. This project demonstrates end-to-end data analysis: preparation, processing, analysis, visualization, and actionable recommendations.

**Key question:** What distinguishes casual riders from annual members, and how can we convert more casual riders into memberships?

**Data source:** [Public Divvy trip data](https://divvy-tripdata.s3.amazonaws.com/index.html)

**Privacy and reproducibility:**
- Aggregated analysis uses only trip-level metadata with no personal/individual identifiers.
- All transformations and workflows are documented in this notebook: [cyclistic_analysis.ipynb](notebooks/cyclistic_analysis.ipynb).
- Processed data outputs are saved to `data/processed/` for downstream use.

---

## 📁 Project Structure

```
bike-share-analysis/
├── data/
│   └── raw/
│       └── [raw datasets]        # GIT ignored due to huge size, download from source URL above if needed
├── notebooks/
│   └── cyclistic_analysis.ipynb  # Main Python-based analysis notebook
├── README.md                     # Project overview and guide
```

---

## 🔍 Analysis Overview

### Data Preparation & Cleaning

- Loaded up to the most recent 12 month data as dataframes.
- Standardized column names, column types, and member/casual labels across dataframes.
- Combined required rows from multiple dataframes into single dataframe, removed exact duplicate rows.
- Viewed summary statistics like row count, columns, data types, and missing values.
- Removed rows with missing values in columns like `ride_id`, `end_station_id`, and `start_station_id` for data quality.
- Derived new features: ride duration in seconds, time features like month and day.
- Converted time features to ordered categorical for consistent ordering.
- Viewed summary statistics of entire dataframe using describe().
- Removed irrelevant records:
  - Rows missing `ride_id`, `end_station_id`, or `start_station_id`.
  - Extreme outliers in ride durations for EDA visuals and summary stats.
  - Trips out of expected date bounds.
- Validated row counts, columns, data types, and missing values again after data cleaning and standardization.
