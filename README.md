# 🚦 Predicting and Preventing Serious Traffic Collisions in Toronto

This project leverages Toronto's Open Data and machine learning techniques to analyze and predict traffic collisions involving serious injuries or fatalities (KSI – Killed or Seriously Injured). By identifying high-risk factors, temporal patterns, and dangerous intersections, we aim to support data-driven interventions for public safety and urban planning.

## 📌 Project Objective

Reduce the number of serious collisions on Toronto roads by:
- Analyzing trends in KSI incidents
- Identifying high-risk behaviors and locations
- Building predictive models to flag potential KSI collisions
- Proposing actionable recommendations

## 🗂️ Datasets Used

- **Motor Vehicle Collisions - KSI**: Includes detailed incident data since 2006 (location, time, conditions, driver behavior, etc.)
- **Speed Data (SVC)**: Aggregated vehicle speeds across intersections
- **Pedestrian Volumes (TMC)**: Pedestrian count data to identify vulnerable hotspots

## 🧹 Data Cleaning & Feature Engineering

- Extracted geographic coordinates using `jsonlite` and `purrr`
- Corrected mislabeled LAT/LONG fields
- Derived temporal features like **Hour of Day** and **Weekday**
- Combined street names into **Intersection**
- Binned age groups and driving behavior categories

## 📊 Exploratory Data Analysis (EDA)

- **Time Analysis**: Peak KSI collisions occur weekdays from 3 PM to 6 PM
- **High-Risk Intersections**: Top 10 hotspots identified and visualized using `leaflet` maps
- **Driver Behavior**:
  - Lost control
  - Speeding
  - Impaired driving
  - Improper lane change
  - Failure to yield
- **Demographics**: Elderly and very young drivers are disproportionately affected

## 🗺️ Geospatial Insights

Mapped KSI incidents to identify clusters:
- Downtown core and arterial roads are high-risk
- Intersections with high speeds and high pedestrian volumes align with KSI hotspots

## 🔍 Modeling & Prediction

### 1. Random Forest Classification
- **Features**: Hour, Weekday, Age Group, Driver Action/Condition, Maneuver
- **Outcome**: KSI flag (1 or 0)
- **Accuracy**: ~83%
- **Top Predictors**:
  - Driver Action
  - Age Group
  - Maneuver
  - Hour of Day

### 2. Logistic Regression
- Estimated **odds ratios** for key factors:
  - Speeding → 3.5× higher risk
  - Lost control → 4.3× higher risk
  - Proper driving → 50% reduced risk

### Confusion Matrix Summary
- Correctly predicted 380 serious collisions
- Flagged 850 non-serious collisions
- Missed 120 serious ones (key area for improvement)
- 150 false positives flagged as serious

## 🛠️ Recommendations

- **Targeted Enforcement**: Increase police presence during peak hours at flagged intersections
- **Intersection Redesign**: Improve safety in high pedestrian zones
- **Driver Education**: Focus campaigns on senior and young driver demographics
- **Future Work**: Integrate real-time traffic and weather data for dynamic predictions

## 📍 Conclusion

Using R and open data, we’ve uncovered actionable insights to reduce KSI collisions in Toronto. This project provides a framework for smarter city planning, public safety strategies, and proactive road interventions.

---

## 🧰 Tech Stack

- R (tidyverse, jsonlite, purrr, leaflet)
- GitHub for version control
- Toronto Open Data Portal

## 📎 License

This project is open-source and available under the MIT License.

## 📬 Contact

For inquiries or collaboration ideas, feel free to reach out via GitHub Issues or submit a pull request!
