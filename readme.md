# ------------------------------------------------------
# Script: setup_github_project.py
# Purpose: Prepare all core files and folders for your GitHub
#          smart meter electricity data analysis project.
# ------------------------------------------------------

import os

# 1. Create necessary directories
os.makedirs('data', exist_ok=True)
os.makedirs('images', exist_ok=True)

# 2. Create README.md with detailed project description
readme_content = """
# Exploratory Analysis of Smart Meter Electricity Data (US)

This project provides an end-to-end Exploratory Data Analysis (EDA) of household electricity consumption using smart meter data. The analysis is performed in a Jupyter Notebook, uncovering consumption patterns, seasonality, anomalies, and actionable insights for utilities and data professionals.

## Table of Contents

- Motivation
- Dataset
- Methodology
- Key Insights
- Visualizations
- Project Structure
- Installation & Setup
- Usage
- Requirements
- Contributing
- License

## Motivation

Understanding granular electricity usage is essential for:
- Utility Companies: Optimizing load forecasting and demand-side management.
- Researchers: Informing energy efficiency and policy studies.
- Data Scientists: Practicing real-world time series analysis, feature engineering, and anomaly detection.

## Dataset

- Source: US household smart meter readings (15-minute intervals).
- Format: CSV files with timestamp, meter ID, and kWh consumed.
- Columns: Timestamp, Meter ID, Usage (kWh)

## Methodology

- Data Ingestion & Cleaning: Load and parse data; handle missing values and outliers.
- Feature Engineering: Extract hour, weekday, month, season; compute rolling statistics.
- Exploratory Analysis: Decompose time series; analyze aggregate stats; detect anomalies.
- Visualization: Plot daily/monthly trends, heatmaps, boxplots, and seasonal patterns.

## Key Insights

- Peak Usage: Evening hours (5–8 PM) see highest consumption.
- Weekly Trends: Usage dips on weekends.
- Seasonality: Increased demand in summer due to cooling needs.
- Anomalies: Spikes outside typical hours may indicate meter issues or special events.

## Visualizations

- Daily & Monthly Trend Plots
- Heatmaps (Hour × Weekday)
- Boxplots (by Month/Day)
- Seasonal Decomposition Plots


## Installation & Setup

1. Clone the repo:
    ```
    git clone https://github.com/Aryanadit/exploratory-smart-meter-electricity.git
    cd exploratory-smart-meter-electricity
    ```
2. (Optional) Create and activate a Python virtual environment:
    ```
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\\Scripts\\activate
    ```
3. Install requirements:
    ```
    pip install -r requirements.txt
    ```

## Usage

1. Place your input CSV files in data/.
2. Start Jupyter Notebook:
    ```
    jupyter notebook
    ```
3. Open and run exploratory-analysis-of-smart-meter-electricity-us.ipynb to reproduce the analysis and generate visualizations.

## Requirements

- pandas >= 1.3.0
- numpy >= 1.21.0
- matplotlib >= 3.4.0
- seaborn >= 0.11.0
- jupyter >= 1.0.0
- scikit-learn >= 1.0.0

## Contributing

Pull requests are welcome!
Please fork the repository, create a feature branch, commit your changes, push to the branch, and open a pull request.


# 3. Create requirements.txt
requirements_content = """
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
jupyter>=1.0.0
scikit-learn>=1.0.0
"""
with open('requirements.txt', 'w') as f:
    f.write(requirements_content.strip())

# 4. Create a placeholder Jupyter Notebook
notebook_content = """{
 "cells": [],
 "metadata": {},
 "nbformat": 4,
 "nbformat_minor": 2
}"""
with open('exploratory-analysis-of-smart-meter-electricity-us.ipynb', 'w') as f:
    f.write(notebook_content)

# 5. (Optional) Print a status message
print("All files and folders created successfully.")
