# Electricity Consumption Profiling and Community-Based Pattern Analysis

This project aims to analyze household electricity consumption patterns using exploratory data analysis (EDA) and graph-based community detection approaches. The analysis focuses on identifying daily usage behaviors, uncovering hidden consumption groups, and generating actionable insights that may support energy efficiency strategies.
The project was conducted using the Individual Household Electric Power Consumption dataset containing more than 2 million observations of electricity usage records.
G. Hebrail and A. Berard. "Individual Household Electric Power Consumption," UCI Machine Learning Repository, 2006. [Online]. Available: https://doi.org/10.24432/C58K54.
## Dataset Information

**Dataset:** Individual Household Electric Power Consumption Dataset

### Original Variables

| Variable | Description |
|----------|-------------|
| datetime | Date and time of observation |
| Global_active_power | Household global active power (kilowatts) |
| Global_reactive_power | Household global reactive power (kilowatts) |
| Voltage | Voltage (volts) |
| Global_intensity | Household current intensity (amperes) |
| Sub_metering_1 | Kitchen energy consumption |
| Sub_metering_2 | Laundry room energy consumption |
| Sub_metering_3 | Water heater and air conditioner consumption |

### Dataset Summary

- Number of observations: **2,075,259**
- Original features: **8**
- Missing values: **25,979 observations (1.25%)**
- Duplicate records: **None detected**

# Project Workflow

## 1. Data Cleaning and Preprocessing

The following preprocessing steps were performed:

- Examined dataset structure and variable types.
- Identified missing values across numerical variables.
- Verified duplicate observations.
- Imputed missing values using:
  - Forward Fill (FFill)
  - Backward Fill (BFill)
- Converted variables into appropriate formats for analysis.
## 2. Feature Engineering

Additional features were created to improve analytical capability.

### Time-Based Features

- Hour
- Day
- Month
- Year
- Day of Week
- Day Name
- Weekend Indicator

### Consumption-Based Features

- Time Category:
  - Dawn
  - Morning
  - Afternoon
  - Evening
- Usage Level:
  - Low
  - Medium
  - High
- Total Sub-metering Consumption
- Other Consumption
After feature engineering, the dataset expanded to **18 variables**.

## 3. Exploratory Data Analysis (EDA)

Several exploratory analyses were conducted to understand electricity consumption behavior.

### Descriptive Statistics

| Metric | Value |
|---------|---------|
| Mean Power Consumption | 1.09 kW |
| Maximum Consumption | 11.12 kW |
| Minimum Consumption | 0.08 kW |
| Standard Deviation | 1.05 kW |

### Exploratory Analyses

- Hourly electricity consumption patterns.
- Peak consumption hour identification.
- Weekday versus weekend consumption comparison.
- Sub-metering contribution analysis.
- General trends in household electricity usage.

## 4. Daily Consumption Profiling

To capture behavioral patterns, minute-level observations were aggregated into daily consumption profiles.

The aggregated data were subsequently normalized to ensure comparability between different consumption scales.

## 5. Graph Construction and Community Detection

To identify groups with similar electricity usage behavior, graph-based community detection techniques were employed.

### Determining Optimal Neighborhood Structure

K-Nearest Neighbors (KNN) was used to construct similarity relationships between daily profiles.

Several values of **K** were evaluated, and the optimal K value was selected using the **Elbow Method**.

## 6. Community Detection Algorithm Comparison
Five community detection algorithms were evaluated:

- Louvain
- Leiden
- Greedy Modularity
- Synchronous Label Propagation
- Asynchronous Label Propagation

Each algorithm was executed **five times**, and the average performance was used for comparison.

### Selected Algorithm

Based on the evaluation results, **Leiden Algorithm** demonstrated the most suitable performance for identifying meaningful communities within the dataset.


## 7. Community Analysis

The identified communities were analyzed through multiple perspectives.

### Community Profiling

- Daily consumption characteristics.
- Average electricity usage patterns.

### 24-Hour Consumption Analysis

- Comparison of hourly behavior across communities.
- Identification of peak demand periods.

### Seasonal Pattern Analysis

- Consumption trends across different periods.

### Weekday vs Weekend Analysis

- Behavioral differences between working days and weekends.

### Similarity Analysis

- Examination of relationships between communities.

### Statistical Testing

- Assessment of significant differences among communities.

### Graph and Network Analysis

- Exploration of network structures formed by daily consumption similarities.

### Peak Usage Prediction

- Identification of periods associated with the highest electricity demand.

The analysis revealed that:

- Household electricity consumption exhibits distinct temporal patterns throughout the day.
- Electricity usage behavior differs between weekdays and weekends.
- Community detection successfully identified groups with similar consumption characteristics.
- Different communities demonstrated unique daily usage profiles, indicating heterogeneous energy behaviors.
- Graph-based approaches provide additional insights beyond traditional descriptive analyses.

# Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- NetworkX
- Matplotlib
- Seaborn
- Jupyter Notebook

## Author

**Ikhda Akmalia Putri**

Fresh Graduate in Information Technology with interests in Data Analytics, Data Science, and Machine Learning.

LinkedIn: www.linkedin.com/in/ikhda-akmalia-putri
