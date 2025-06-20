# ✈️ Flight Delay Analysis & Prediction

> **Can we crack the code behind flight delays and help revolutionize air travel?**  
> I set out to answer that question by digging into one year of U.S. domestic flight data, surfacing bottlenecks, and training models that predict delays *before* they happen.

---

## 📖 Background  

Flight delays frustrate passengers and cost airlines millions.  
As a Data Analyst on a major U.S. carrier’s analytics team, my mission is to:

1. **Diagnose** operational pain-points (routes, times, carriers, airports)  
2. **Forecast** departure delays ≥ 15 minutes  
3. **Recommend** data-driven actions that improve on-time performance and passenger satisfaction  

---

## 💾 Dataset  

| File | Description |
|------|-------------|
| **`flights.csv`** | ~ N rows of historic flight records |
| **`airlines_carrier_codes.csv`** | Lookup table for carrier → airline name |

### Key columns

| Column | Meaning |
|--------|---------|
| `dep_delay`, `arr_delay` | Delay in minutes (departure / arrival) |
| `carrier`, `flight`, `tailnum` | Airline & aircraft identifiers |
| `origin`, `dest` | 3-letter airport codes |
| `air_time`, `distance` | Flight duration (min) & distance (mi) |
| `year · month · day · hour · minute` | Date-time components for temporal analysis |

---

## 💪 Business Questions  

1. **Airline Punctuality** – Which carriers excel (or struggle) with on-time departures/arrivals and how does that vary month-to-month?  
2. **Temporal Trends** – Are there specific months, weeks, or times of day when delays spike?  
3. **Airport Performance** – Which airports run like clockwork, and which cause systemic disruptions?  
4. **(Optional 1)** *Prediction* – Can we predict whether a flight will depart ≥ 15 minutes late?  
5. **(Optional 2)** *Driver Analysis* – Which features (route, distance, time of day, carrier, …) influence delays the most?

---

## 🛠️ Tools & Libraries  

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-0D76A8?style=for-the-badge&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit-learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-00599C?style=for-the-badge&logo=data:image/png;base64,iVBORw0KGgo=) <!-- tiny blank logo -->
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

---

## 🔍 Approach  

| Stage | Key Tasks |
|-------|-----------|
| **1 · Data Cleaning** | ▸ Parse dates & times<br>▸ Handle missing values<br>▸ Remove extreme outliers |
| **2 · EDA** | ▸ Aggregate delay metrics by carrier / month / hour<br>▸ Visualize heat-maps & boxplots to spot patterns |
| **3 · Feature Engineering** | ▸ Binary target `is_delayed_15`<br>▸ Temporal features (day-of-week, season)<br>▸ Route pair `origin-dest` |
| **4 · Modeling** | ▸ Baseline: Logistic Regression<br>▸ Tree-based: Random Forest, XGBoost |
| **5 · Evaluation** | ▸ Train/test split (80/20)<br>▸ Metrics: ROC-AUC, F1, accuracy<br>▸ Explainability: feature importance |
| **6 · Insights + Recommendations** | ▸ Rank worst airports & carriers<br>▸ Suggest schedule tweaks and buffer times |

---

## 📊 Results & Insights  

> _Replace the bullets below with your actual findings once you run the notebook._

* **XGBoost ROC-AUC:** **0.82** (↑ 15 pp over baseline)  
* **Top delay drivers:** late inbound aircraft, peak-hour congestion, long-haul routes  
* **Worst-performing hub:** _XXX_ – 35 % of flights depart ≥ 15 min late  
* **Best on-time carrier:** _YYY_ – maintains sub-6 min median departure delay year-round  

See the full analysis in **`flight_delay_analysis.ipynb`**.

---

## 🗂 Repository Structure  

