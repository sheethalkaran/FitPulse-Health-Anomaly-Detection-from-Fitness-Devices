# FitPulse Health Anomaly Detection – Milestone 1

## Project Overview

**FitPulse Health Anomaly Detection** focuses on preprocessing and structuring wearable fitness data to support future health anomaly detection tasks.

**Milestone 1** covers **data ingestion, cleaning, timestamp normalization, and consolidation** of multiple wearable fitness datasets. The objective is to generate a **clean, unified dataset** containing heart rate, physical activity, and sleep metrics, standardized to **1-minute intervals**, and prepared for subsequent analysis or machine learning stages.


## Dataset Availability

Due to repository size limitations, **raw datasets are not included** in this GitHub repository.
The datasets used in this milestone are **publicly available wearable fitness datasets** accessed from Kaggle:
🔗 **Kaggle Dataset**  
https://www.kaggle.com/datasets/monicamd/fit-base-data


## Datasets Used

This milestone utilizes **public wearable fitness data** consisting of heart rate, step count, and sleep information collected from multiple users.

### 1. Heart Rate  
**File:** `heartrate_seconds_merged.csv`  
- Columns: `Id`, `Time`, `Value`  
- Contains heart rate measurements recorded at **second-level intervals** per user.

### 2. Steps  
**File:** `minuteStepsNarrow_merged.csv`  
- Columns: `Id`, `ActivityMinute`, `Steps`  
- Records step counts at **minute-level intervals** per user.

### 3. Sleep  
**File:** `sleepDay_merged.csv`  
- Columns: `Id`, `SleepDay`, `TotalMinutesAsleep`  
- Contains **daily sleep duration data** per user.


## Tools and Technologies

- Python 3.x  
- Pandas  
- NumPy  
- Matplotlib  
- Google Colab  


## Preprocessing Workflow

All preprocessing steps are implemented entirely in **Google Colab**, without any frontend or UI components.

1. Load datasets using Pandas (`pd.read_csv`).  
2. Convert timestamp fields to **Pandas `datetime` format** and normalize them to **UTC**.  
3. Handle missing and null values:
   - **Heart Rate:** forward-filled (`ffill`) to maintain temporal continuity  
   - **Steps:** missing minute-level values filled with `0`  
   - **Sleep:** retained as `NaN` where unavailable to preserve analytical integrity  
4. Resample metrics to a **consistent 1-minute interval**:
   - Heart Rate: mean value per minute  
   - Steps: total steps per minute  
5. Merge datasets:
   - Heart rate and steps aligned by **user (`Id`)** and timestamp  
   - Daily sleep data merged by **user (`Id`)** and date  
6. Perform final sorting, validation, and consistency checks.  
7. Save the cleaned and consolidated dataset to **Google Drive**.  
8. Generate basic visualizations:
   - Heart rate trends over time  

## Observations

- Heart rate data is highly granular and required aggregation from seconds to minutes.  
- Steps data is primarily minute-based, with missing intervals handled appropriately.  
- Sleep data is recorded at a daily level and serves as contextual information for analysis.



## Acknowledgment

This project was developed as part of the **Infosys Springboard Internship Program**.
