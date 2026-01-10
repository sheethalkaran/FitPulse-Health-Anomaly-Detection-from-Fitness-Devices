# FitPulse Health Anomaly Detection from Fitness Devices  
## Milestone 4: Dashboard for Insights

## Objective
The objective of Milestone 4 is to develop an interactive dashboard for visualizing and analyzing health anomalies detected from wearable fitness device data. This milestone deploys the feature extraction, trend modeling, and anomaly detection logic developed in Milestones 2 and 3 into a real-time, user-friendly Streamlit dashboard executed using Google Colaboratory.

## Dashboard Workflow
1. Upload fitness data files (CSV or JSON) through the Streamlit dashboard interface.
2. Validate dataset structure and preprocess timestamps for time-series analysis.
3. Select user ID, health metric (Heart Rate, Steps, or Sleep Duration), and date range using interactive sidebar controls.
4. Apply Prophet-based time-series forecasting to model expected behavioral trends.
5. Compute residuals between observed and predicted values.
6. Detect anomalies using statistical thresholding and Prophet confidence interval violations, consistent with Milestone 3 methodology.
7. Visualize metric trends with highlighted anomaly markers for clear interpretation.
8. Generate and download a CSV-based anomaly summary report containing timestamps and metric-level insights.

## Tools & Libraries Used
- Python  
- Google Colaboratory  
- Streamlit  
- Pandas and NumPy  
- Prophet (time-series forecasting and residual analysis)  
- Plotly (interactive visualizations)

## Key Insights from the Dashboard
- Heart rate anomalies are observed as sudden spikes or drops that significantly deviate from expected physiological trends.
- Sleep anomalies highlight irregular sleep behavior, including unusually low or inconsistent sleep duration.
- Step count anomalies indicate abnormal activity patterns such as prolonged inactivity or unexpected surges.
- Interactive metric-wise and date-wise filtering enables focused analysis of individual user health patterns.

## Screenshot References
- **screenshots/dashboard_ui.png**: Shows the Streamlit dashboard interface with dataset upload options, filters, summary metrics, and interactive anomaly visualizations.
- **screenshots/report_download.png**: Displays the anomaly summary report being generated and downloaded from the dashboard.
