# Bike-share Analysis

A comprehensive analysis of bike-share data to understand user behavior and improve business strategies. This project demonstrates end-to-end data analysis: preparation, processing, analysis, visualization, and actionable recommendations. The analysis uses [Divvy/Chicago bike-share trip data](https://divvy-tripdata.s3.amazonaws.com/index.html) as a realistic proxy for Cyclistic.

**Key question:** What distinguishes casual riders from annual members, and how can we convert more casual riders into memberships?

**Privacy and reproducibility:**
- This aggregated analysis uses only trip-level metadata with no personal/individual identifiers.
- Raw data files are expected under `data/raw/` (this directory is git-ignored due to file size). Download the datasets from the source URL above and store each file using the following structure: `data/raw/{YYYYMM}-divvy-tripdata/{YYYYMM}-divvy-tripdata.csv`, where `YYYYMM` represents the year and month (e.g., `202601`).
- All transformations and analysis are documented in [cyclistic_analysis.ipynb](notebooks/cyclistic_analysis.ipynb).
- Processed data outputs are saved to `data/processed/` for downstream use.

---

## 📁 Project Structure

```
bike-share-analysis/
├── data/
│   └── raw/
│       └── [raw datasets]        # git-ignored, download from source URL above if needed
├── notebooks/
│   └── cyclistic_analysis.ipynb  # Main Python-based analysis notebook
├── README.md                     # Project overview and guide
```

---

## 🔍 Analysis Overview

### Data Preparation & Cleaning

- Loaded up to the most recent 12 month(s) data as dataframes.
- Standardized column names, column types, and member/casual labels across dataframes.
- Combined required columns from multiple dataframes into a single dataframe, removed exact duplicate rows.
- Viewed summary statistics like row count, columns, data types, and missing values.
- Removed rows with missing values in columns like `ride_id`, `end_station_id`, and `start_station_id` for data quality.
- Derived new features: ride duration in seconds, time features like month and day.
- Converted time features to ordered categorical for consistent ordering.
- Viewed summary statistics of entire dataframe using describe().
- Removed trips with negative or zero ride durations.
- Removed top 1% ride durations as extreme outliers.
- Removed trips that started out of expected date bounds.
- Reviewed summary statistics again after data cleaning and standardization. Yes! data is clean now.
