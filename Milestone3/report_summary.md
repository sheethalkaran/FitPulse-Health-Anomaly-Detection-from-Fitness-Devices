# FitPulse Health Anomaly Detection from Fitness Devices  
## Milestone 3: Anomaly Detection and Visualization

## Objective
The objective of Milestone 3 is to detect, label, and visualize anomalies in wearable fitness data using time-series forecasting and unsupervised learning techniques. This milestone builds on the trend models and behavioral patterns identified in Milestone 2 to highlight abnormal physiological and behavioral events related to heart rate and sleep activity.

## Dataset Description
The analysis uses the cleaned and reduced dataset generated in Milestone 2. The dataset consists of minute-level fitness data for multiple users and includes heart rate, step count, and total minutes asleep. The data contains no missing values and is suitable for time-series analysis and anomaly detection.

A reduced dataset was intentionally used in this milestone to ensure computational efficiency and clarity of anomaly detection results, while preserving the temporal structure required for validation and visualization.

## Methodology and Steps Followed

### Residual Analysis Using Prophet
Time-series forecasting models were developed using the Prophet library for heart rate and sleep metrics. Predicted values were compared with actual observations to compute residuals, representing deviations from expected physiological behavior.

### Threshold-Based Anomaly Detection
Statistical thresholds were applied to residual values using standard deviation–based limits. Prophet confidence intervals were also used to identify violations where observed values fell outside the expected range. For sleep data, domain-specific rules were applied to detect abnormal patterns such as zero sleep duration or sudden drops in sleep minutes.

### Cluster-Based Anomaly Detection
User-level behavioral features were aggregated and standardized before applying Principal Component Analysis (PCA) for dimensionality reduction. DBSCAN clustering was then used to identify users exhibiting outlier behavioral patterns. Users classified as noise points were flagged as cluster-based anomalies.

### Anomaly Labeling
Anomalies detected through residual analysis, threshold-based rules, and clustering were combined to generate clear labels. Separate indicators were maintained for heart rate anomalies, sleep anomalies, and cluster-based anomalies, along with a final anomaly label distinguishing normal and abnormal observations.

### Visualization of Anomalies
Time-series visualizations were created for heart rate and sleep metrics. Anomalous data points were highlighted using alert markers to clearly indicate abnormal segments. These visualizations help in understanding the timing and nature of detected anomalies.

## Tools and Libraries Used
The analysis was performed using Python in Google Colaboratory with the following libraries:
- Pandas and NumPy for data manipulation
- Prophet for time-series forecasting
- Scikit-learn for PCA and clustering
- Matplotlib and Seaborn for visualization

## Key Insights and Observations
Heart rate anomalies were observed as sudden spikes or drops that significantly deviated from predicted trends. Sleep anomalies were primarily identified during periods of zero or abruptly changing sleep duration, indicating irregular sleep behavior. Cluster-based analysis revealed users with distinct behavioral patterns compared to the majority, supporting the anomaly detection results obtained from residual and threshold-based methods.

## Outputs
The following outputs were generated as part of this milestone:
- Heart rate time-series chart with highlighted anomalies
- Sleep pattern visualization showing abnormal segments

These visualizations are saved in the `visualizations/` directory and provide clear evidence of detected anomalies.
