# Milestone 2: Feature Extraction and Modeling

## Project: FitPulse – Health Anomaly Detection from Fitness Devices


## Objective
The objective of Milestone 2 is to extract meaningful features from preprocessed fitness data, model temporal trends, and identify behavioral patterns using statistical and machine learning techniques. This milestone provides the analytical foundation required for anomaly detection in subsequent stages of the project.


## Dataset Description
A reduced and validated dataset derived from Milestone 1 is used to ensure consistency, clarity, and reproducibility.

**Dataset characteristics:**
- 5 unique users
- 15 timestamped observations per user
- Minute-level time-series data
- No missing values

**Dataset columns:**
- `DateTime`: Timestamp of the observation  
- `Id`: Unique user identifier  
- `HeartRate`: Heart rate measurement  
- `Steps`: Step count  
- `TotalMinutesAsleep`: Total sleep duration during sleep periods (0 during awake periods)

**Dataset path:**
```
data/milestone2_reduced_fitness_data.csv
```



## Methodology

### Feature Extraction
Automated time-series feature extraction was performed using TSFresh on heart rate, steps, and sleep data. Extracted features include statistical measures, change-based features, and frequency-domain characteristics such as entropy. Missing values generated during extraction were handled using TSFresh imputation utilities.


### Feature Selection
Variance thresholding was applied to eliminate low-variance and non-informative features, reducing dimensionality while preserving key behavioral information required for modeling.


### Trend Modeling
Temporal trend modeling was performed using Facebook Prophet for heart rate, steps, and sleep metrics. Forecasts were generated along with confidence intervals, and residuals were computed to quantify deviations between observed and predicted values.


### Dimensionality Reduction
Principal Component Analysis (PCA) was applied to reduce the high-dimensional feature space to two components, enabling effective visualization and interpretation of behavioral patterns.

### Behavioral Pattern Clustering
KMeans clustering was used to group users based on behavioral similarity. DBSCAN was applied as a complementary technique to identify potential outliers. The resulting clusters represent distinct behavioral patterns, including normal and atypical behavior.


## Tools and Libraries
- Python
- pandas, numpy
- matplotlib, seaborn
- scikit-learn
- tsfresh
- prophet

## Key Observations
- Automated feature extraction generated a rich set of statistical and frequency-domain features.
- Feature selection significantly reduced dimensionality while retaining relevant behavioral characteristics.
- Trend modeling captured short-term temporal patterns and uncertainty.
- Dimensionality reduction and clustering revealed clear separation between user behavioral profiles.
- Residual analysis provides a basis for anomaly detection in future milestones.

## Conclusion
This milestone demonstrates a structured and reproducible approach to feature extraction, trend modeling, and behavioral pattern analysis using time-series fitness data. The results form a robust analytical foundation for subsequent anomaly detection tasks.
