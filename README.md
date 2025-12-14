# FitPulse Health Anomaly Detection - Milestone 1

## Project Overview

This project is part of the **FitPulse Health Anomaly Detection** initiative.  
Milestone 1 focuses on **data ingestion, preprocessing, and time normalization** of fitness datasets collected from wearable devices. The goal is to generate a **clean, consolidated dataset** of heart rate, steps, and sleep data, resampled to **1-minute intervals**, ready for further analysis or anomaly detection.

---

## Dataset Availability

Due to file size constraints, raw datasets are **not stored in this GitHub repository**.

All datasets used in this project are publicly available and can be accessed from the official source:

🔗 **Fitabase Dataset (Kaggle)**: [https://www.kaggle.com/datasets/monicamd/fit-base-data](https://www.kaggle.com/datasets/monicamd/fit-base-data)

---

## Datasets Used

The project uses **three datasets** from **Fitabase**:

1. **Heart Rate** (`heartrate_seconds_merged.csv`)  
   - Columns: `Id`, `Time`, `Value`  
   - Contains heart rate measurements at **second-level intervals** per user.

2. **Steps** (`minuteStepsNarrow_merged.csv`)  
   - Columns: `Id`, `ActivityMinute`, `Steps`  
   - Contains step counts at **minute-level intervals** per user.

3. **Sleep** (`sleepDay_merged.csv`)  
   - Columns: `Id`, `SleepDay`, `TotalMinutesAsleep`  
   - Contains **daily sleep data** per user.

---

## Preprocessing Workflow

The preprocessing steps are implemented entirely in **Google Colab**, without any UI or frontend.

1. **Load datasets** using Pandas (`pd.read_csv`).  
2. **Convert timestamps** to Pandas `datetime` format in UTC.  
3. **Handle missing/null values**:
   - Heart Rate: forward-fill (`ffill`)  
   - Steps: missing minutes filled with `0`  
   - Sleep: retained as daily context  
4. **Resample metrics** to **1-minute intervals**:
   - Heart Rate: average per minute  
   - Steps: sum per minute  
5. **Merge datasets**:
   - Heart rate and steps aligned per **user (`Id`)** and per minute  
   - Daily sleep merged by `Id` and date  
6. **Sort and clean** the final dataset.  
7. **Save the cleaned dataset** to Google Drive.  
8. **Visualizations**:
   - Heart Rate trend  

