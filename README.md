# 🚦 Predicting and Preventing Serious Traffic Collisions in Toronto

Hi! I created this project to explore serious traffic collisions in Toronto using open data and machine learning in R. My goal was to identify patterns, pinpoint dangerous intersections, and propose actionable solutions to help reduce injuries and fatalities on city streets.

## 📌 What I Set Out to Do

I wanted to:
- Understand when and where serious collisions happen
- Explore how driver behavior and demographics contribute to risks
- Build predictive models to highlight where interventions could be most effective
- Use insights to support smarter urban planning and safety initiatives

## 🗂️ Data Sources I Used

- **KSI Collisions Dataset**: Rich historical data since 2006 on incidents involving people killed or seriously injured
Source: https://open.toronto.ca/dataset/motor-vehicle-collisions-involving-killed-or-seriously-injured-persons/

## 🧹 How I Cleaned and Prepared the Data

- Extracted coordinates from geometry fields using `jsonlite` and `purrr`
- Corrected mislabeled LAT/LONG columns
- Engineered new features like:
  - **Hour of day** and **Weekday**
  - **Intersection name** from Street1 + Street2
  - **Age groups** and binned **driver behaviors**

## 📊 What the Initial Data Told Me

- **Rush Hour Risk**: Most serious collisions happen weekdays between 3 PM and 6 PM
- **Danger Zones**: I mapped and ranked the top 10 high-risk intersections using `leaflet`
- **Driver Behavior Matters**:
  - Lost control
  - Speeding
  - Impaired driving
  - Improper lane change
  - Failure to yield
- **Demographic Patterns**: Elderly (65+) and very young drivers (<20) are disproportionately represented

## 🗺️ Geospatial Discoveries

I found clustering of incidents around downtown and high-speed roads. Collisions were more frequent:
- At intersections with higher traffic speeds
- Where pedestrian volumes were high — making these hotspots particularly dangerous for vulnerable road users

## 🔍 Modeling & Prediction Techniques

### 🔢 Random Forest Classification
- Trained on features like time, age group, driver actions and maneuvers
- Output was a binary KSI flag (1 or 0)
- Achieved ~83% accuracy
- Top predictors:
  - Driver Action
  - Age Group
  - Maneuver
  - Hour of Day

### 📈 Logistic Regression
- Used to estimate odds ratios:
  - Speeding increased KSI risk by 3.5×
  - Losing control raised the odds by 4.3×
  - Proper driving behavior reduced risk by ~50%

### Confusion Matrix Snapshot
- Correctly predicted 380 serious collisions
- Got 850 non-serious ones right
- Missed 120 serious collisions — a key area for improvement
- Flagged 150 non-serious incidents as serious

## 🛠️ What I Recommend

- **Focused Enforcement**: Increase patrols and install cameras at high-risk spots during peak hours
- **Intersection Redesigns**: Especially at locations with heavy pedestrian traffic
- **Targeted Driver Education**: For seniors and young drivers
- **Future Work**: Bring in real-time traffic and weather data to sharpen predictions

## 🧰 Tools I Used

- R and tidyverse for data wrangling
- jsonlite and purrr for JSON parsing
- leaflet for interactive mapping
- Toronto Open Data Portal for public datasets

## 📎 License

MIT License — feel free to use, share, and build on this project.

## 📬 Connect With Me

If you’re interested in collaborating, improving the models, or applying similar techniques to another city, reach out via GitHub Issues or submit a pull request. I'd love to explore new ways to make urban transportation safer.
