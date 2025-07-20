# ⚡ Exploratory Analysis of Smart Meter Electricity Data (US)

![Smart Meter Analysis Banner](images/banner.png)

---

## 📝 Project Overview

This repository provides an in-depth, visually driven exploratory data analysis (EDA) of hourly electricity consumption recorded by smart meters in U.S. households. Leveraging time-series techniques, statistical summaries, and illustrations, the project reveals critical usage patterns, seasonal effects, anomalies, and actionable insights tailored for:

- **⚡ Utility providers** — optimize grid operations and resource planning
- **🔬 Researchers** — understand energy demand on a granular scale
- **📊 Data scientists** — build, validate, or benchmark forecasting models
- **🏛️ Policy makers** — assess impact of demand-management programs

---

## 🔍 Motivation

Modern smart meters capture electricity usage at high time resolution, unlocking the ability to:

- **Track daily/weekly cycles:** Morning/evening demand peaks, weekday vs. weekend profiles
- **Visualize seasonality:** Detect summer cooling or winter heating loads
- **Spot outliers/anomalies:** Identify meter issues or extreme usage events
- **Assess long-term trends:** See the evolution of baseline demand over years

By analyzing and visualizing these dynamics, stakeholders are empowered to make data-driven decisions for demand response, infrastructure upgrades, and effective customer outreach.

---

## ⚙️ Installation & Setup

1. **Clone the repository:**
git clone https://github.com/Aryanadit/Exploratory-Analysis-of-Smart-Meter-Electricity-Data.git
cd Exploratory-Analysis-of-Smart-Meter-Electricity-Data

2. **(Optional) Create & activate a virtual environment:**
python3 -m venv venv
source venv/bin/activate # On Windows: venv\Scripts\activate

3. **Install dependencies:**
pip install -r requirements.txt

4. **Download smart meter data:**
- Use datasets such as the [London Smart Meter Dataset](https://data.london.gov.uk/dataset/smartmeter-energy-use-data-in-london-households)
- Place CSV files in the `data/` directory (e.g., `data/consumption.csv`)

5. **Launch the analysis notebook:**
jupyter notebook exploratory-analysis-of-smart-meter-electricity-us.ipynb

---

## 🚦 Notebook Walkthrough

1. **Data Loading & Cleaning**
- Import CSVs, parse timestamps, clean missing or duplicate entries
- Resample to hourly intervals

2. **Descriptive Statistics**
- Calculate mean, median, standard deviation
- Plot histograms and boxplots to check distribution and outliers

3. **Time-Series Visualization**
- Line plots for daily, weekly, monthly trends
- Overlay daily cycles and generate hour-vs-month heatmaps

4. **Seasonal Decomposition (STL)**
- Decompose series into trend, seasonal, and residuals

5. **Anomaly Detection (Optional)**
- Flag high/low readings using Z-scores or IQR thresholds

---

## 🌟 Key Insights

- **Peak Usage:** Highest consumption between 6–9 PM (especially on weekdays)
- **Seasonality:** Summer afternoons show usage surges (air conditioning loads)
- **Weekly Trends:** Slight dip in demand on weekends
- **Anomalies:** Occasional outlier days often signal meter faults or unique events

---

## 📈 Visualizations

- Daily and monthly trend line plots
- Heatmaps visualizing hourly consumption across weeks/months
- Boxplots to compare daily and monthly distributions
- STL plots showing trend and seasonality

_Example output figures are saved in the `images/` folder. Run the notebook to regenerate plots._

---

