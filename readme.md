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

# 📒 Notebook Walkthrough

This notebook guides you through a comprehensive exploratory analysis of US Smart Meter Electricity Data, followed by straightforward machine learning experiments for short-term consumption forecasting.

---

## 1️⃣ Data Preprocessing

- **Data Loading:** Imported household electricity usage data from CSV files.
- **Datetime Indexing:** Merged separate Date and Time columns into a unified `Datetime` index for effective time-series handling.
- **Numeric Conversion & Cleaning:** Converted all readouts to numeric format; cleaned the data by dropping rows with missing values.
- **Resampling Preparation:** Prepared the dataset for easy aggregation by day, week, month, or year.

---

## 2️⃣ Exploratory Data Analysis (EDA)

### Daily Consumption Aggregation
- Transformed `Global_active_power` (kW) to per-interval `Energy_kWh`.
- Aggregated data by day to compute total energy consumption.
- Visualized daily trends with line plots.

### Descriptive Statistics
- Generated summary statistics using `.describe()` to understand data distribution.
- Visualized the distribution of `Global_active_power` using histograms and kernel density estimates (KDE).

### Time-Series Visualization
- Plotted `Global_active_power` over the full timeline to spot trends or anomalies.

### Sub-Metered Consumption Breakdown
- Visualized energy use over time for:
   - **Kitchen:** `Sub_metering_1`
   - **Laundry Room:** `Sub_metering_2`
   - **Water Heater & AC:** `Sub_metering_3`

---

## 3️⃣ Time Aggregation Insights

- **Daily:** Plotted trends for each sub-meter to observe day-to-day appliance usage.
- **Weekly:** Smoothed series to highlight longer-term patterns and weekly cycles.
- **Monthly:** Visualized seasonal effects and changing demands.
- **Yearly:** Calculated total energy used per year for long-term perspective.

---

## 4️⃣ Pattern & Distribution Analysis

- **Appliance Consumption Pie Chart:** Illustrated how total energy use is distributed across kitchen, laundry, and heating/cooling.
- **Hourly Usage Profiles:** Explored average hourly consumption curves for all three sub-meters.
- **Weekday vs Weekend Comparison:** Compared energy usage to reveal behavioral differences.

---

## 🔮 Forecasting: Next-Week Hourly Consumption

### Data Preparation
- Leveraged hourly-aggregated data (`smart_meter_aggregated.csv`).
- Focused on predicting `Global_active_power`.

### Feature Engineering
- Created lag features (`lag_1` to `lag_24`) to incorporate the effect of the previous 24 hours.
- Removed rows with missing lag data to ensure model readiness.

### Train-Test Split
- Reserved the most recent 7 days (168 hours) for model testing.
- Employed time-aware (chronological) data split to prevent data leakage.

---

## 🧑‍💻 Models Trained

- **Random Forest Regressor**
   - Trained on lagged hourly features.
   - Forecasted the next week’s hourly consumption.
   - Evaluated using MAE, RMSE, and R² metrics.
- **XGBoost Regressor**
   - Trained and evaluated in the same way.
   - Served as a benchmark for comparison.

---

## 📊 Evaluation & Visualization

- Plotted Actual vs. Predicted hourly consumption for the test week to visually assess both models.
- Compared model performance (MAE, RMSE, R²) side by side.
- Created bar charts summarizing the comparative results.

---

## 📝 Key Takeaways

- The notebook thoroughly explores and visualizes energy usage patterns at daily, weekly, monthly, and yearly levels.
- Short-term forecasts using tree-based regressors (Random Forest, XGBoost) provide reasonable accuracy for operational use.
- Appliance-level breakdowns expose detailed consumption trends and user habits.
- Models capture overall electricity demand patterns but may struggle with abrupt spikes or anomalous events not present in the historical data.

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

