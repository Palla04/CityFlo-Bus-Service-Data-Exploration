# CityFlo Bus Service — Metro Cities Analytics & Dashboard

## Project Overview

This project presents an end-to-end **Exploratory Data Analysis (EDA), data cleaning, statistical analysis, KPI design, and dashboard development** workflow for a synthetic CityFlo-style premium bus service operating across six Indian metropolitan cities in 2024. The analysis focuses on understanding operational reliability, demand, revenue, pricing, fleet utilization, cancellations, and customer experience, and converts these findings into four interactive analytical dashboards.

## Dataset Link

**Kaggle Dataset:** [CityFlo Bus Service — Metro Cities](https://www.kaggle.com/datasets/satyakidas07/cityflow-bus-service-metro-cities)

## Project Files

### Raw Data

- **cityflo_bus_service_metro_cities.csv** – Original dataset before any processing.

### Cleaned Dataset

- **cityflo_bus_service_metro_cities_cleaned.csv** – Contains the cleaned and standardized dataset used for the analytical workflow.

### Data Analysis

- **cityflo-data-analysis.ipynb** – Jupyter Notebook containing the complete data-cleaning, exploratory analysis, statistical testing, KPI calculation, and visualization workflow.

### Dashboards

Contains the four dashboard visualizations and the exported dashboard report:

- `Dashboard_1_Operational_Overview.jpg`
- `Dashboard_2_City_Booking_Performance.jpg`
- `Dashboard_3_City_Revenue_Performance.jpg`
- `Dashboard_4_Pricing_Occupancy_Analysis.jpg`
- `Cityflo Bus Service Data Analysis Dashboard.pdf`

---

### Other Project Files

- `.gitignore` — Git ignored files and folders
- `LICENSE` — Project license
- `requirements.txt` — Python dependencies
- `README.md` — Project documentation

---

## Data Cleaning Process

The raw dataset contained intentionally messy and inconsistent values to simulate real-world data-quality issues.

The cleaning process included:

- Identifying and removing **58 duplicate records** using `trip_id`.
- Standardizing text fields and categorical labels.
- Normalizing Boolean fields such as `is_peak_hour`, `gps_enabled`, and `complaint_raised`.
- Cleaning `fare_inr` values containing currency symbols, commas, and text-based numeric formats.
- Handling invalid ages, non-positive fares, occupancy issues, and fare outliers.
- Reviewing missing-value patterns and handling them according to business meaning.
- Converting `trip_date` and operational timestamp fields into appropriate datetime formats.
- Creating derived fields including:
  - `trip_year`
  - `trip_month`
  - `trip_weekday`
  - `delay_minutes`
  - `net_revenue_inr`
  - Age groups
- Defining a trip as delayed when `delay_minutes > 5`.

After cleaning, the analytical dataset contained **3,200 unique trip records**.

---

## Data Analysis (.ipynb)

The complete analysis is available in:

`Data Analysis/cityflo-data-analysis.ipynb`

The notebook follows an end-to-end analytical workflow:

**Data Inspection → Data Quality Assessment → Data Cleaning → Feature Engineering → EDA → Statistical Testing → KPI Definition → Dashboard Development**

The analysis includes:

- Univariate analysis
- Bivariate analysis
- Multivariate analysis
- Descriptive statistics
- Distribution analysis
- City-level comparisons
- Fare and distance analysis
- Bus-type pricing analysis
- Trip-status analysis
- Occupancy analysis
- Customer-experience analysis
- Correlation analysis
- Hypothesis testing
- KPI calculation

---

### Statistical Tests

The notebook includes:

1. **Pearson Correlation** — Distance vs Fare
2. **Independent t-test** — Peak vs Non-Peak Delay
3. **One-Way ANOVA** — Fare by Bus Type
4. **Chi-Square Test** — City vs Trip Status

---

## Live Dashboard & Visuals

**Live Dashboard:** [View Live Dashboard](https://datastudio.google.com/reporting/ca845f5a-e477-4f1d-a769-157a6abada13)

### Dashboard 1 — Operational Overview

![Dashboard 1 — Operational Overview](Dashboards/Dashboard_1_Operational_Overview.jpg)

Provides an executive-level overview of:

- Revenue
- Trip volume
- Completed trips
- On-time performance
- Cancellation rate
- Average fare
- Average rating
- Occupancy
- Complaint rate

### Dashboard 2 — City & Booking Performance

![Dashboard 2 — City & Booking Performance](Dashboards/Dashboard_2_City_Booking_Performance.jpg)

Focuses on:

- Trip volume by city
- Booking outcomes
- Fare vs distance
- Payment-method usage
- City-level booking performance

### Dashboard 3 — Revenue, Occupancy & City Performance

![Dashboard 3 — Revenue, Occupancy & City Performance](Dashboards/Dashboard_3_City_Revenue_Performance.jpg)

Focuses on:

- City-level revenue
- Occupancy
- Trip volume
- Trip status
- Booking-channel revenue

### Dashboard 4 — Pricing, Cancellations & Occupancy

![Dashboard 4 — Pricing, Cancellations & Occupancy](Dashboards/Dashboard_4_Pricing_Occupancy_Analysis.jpg)

Focuses on:

- Bus-type pricing
- Cancellation and no-show patterns
- Occupancy vs average fare
- City-level pricing and utilization

---

## Dataset Summary

| Attribute | Value |
|---|---:|
| Raw records | 3,258 |
| Raw columns | 36 |
| Duplicate rows identified | 58 |
| Final unique trip records | 3,200 |
| Cities | 6 |
| Routes | 60 |
| Bus types | 4 |
| Unique customers | 1,251 |
| Analysis period | 2024 |
| Dataset type | Synthetic / Educational |

**Cities:** Mumbai, Pune, Bangalore, Chennai, Hyderabad, Delhi NCR

**Main data domains:** Trips, customers, routes, fares, discounts, payments, booking channels, trip status, cancellations, ratings, occupancy, weather, peak-hour indicators, subscriptions, GPS availability, and complaints.

---

## Method

The project uses Python-based data analysis and preprocessing with **Pandas, NumPy, Matplotlib, Seaborn, and SciPy**, supported by Microsoft Excel for cleaned-data handling and validation. The cleaned data was explored through descriptive statistics and visual analysis, followed by statistical hypothesis testing and KPI development. The resulting analytical outputs were transformed into four interactive dashboards using **Looker Studio**.

**Notebook:** [Open the analysis notebook](https://www.kaggle.com/code/biswas2022/cityflo-data-exploration)

---

### Key KPIs

| KPI | Value |
|---|---:|
| Total Revenue | ₹859,623.50 |
| Total Trips | 3,200 |
| Completed Trips | 2,494 |
| On-Time Performance | 68.75% |
| Cancellation Rate | 22.06% |
| Average Fare | ₹317.68 |
| Average Rating | 3.80 / 5 |
| Average Occupancy | 57.86% |
| Complaint Rate | 6.41% |

---

## Recommendations

### Reduce Cancellations & No-Shows
**Evidence:** Cancellation rate is **22.06%**; Delhi NCR has the highest cancellations (**74**) and Pune the highest no-shows (**65**).

Use reminders, clearer cancellation communication, and city-specific leakage analysis.

### Improve Operational Reliability
**Evidence:** On-time performance is **68.75%** with an average delay of **5.21 minutes**.

Analyze delays by route, city, bus type, weather, and departure time.

### Optimize Fleet Capacity
**Evidence:** Average occupancy is **57.86%**.

Review utilization by route, city, weekday, bus type, and peak period to improve scheduling.

### Differentiate Pricing by Bus Type
**Evidence:** ANOVA shows a significant fare difference across bus types; Premium AC averages **₹379.3**.

Evaluate fare elasticity, occupancy, and revenue by bus type.

### Investigate Delhi NCR
**Evidence:** Delhi NCR has the lowest displayed net revenue (**₹125.5K**), highest cancellations (**74**), and lowest displayed average fare (**₹282**).

Investigate route-level performance before making operational decisions.

### Evaluate High-Volume Markets
**Evidence:** Mumbai has **553 trips / ₹157.0K** revenue and Pune has **552 trips / ₹153.2K**.

Evaluate capacity, route coverage, and revenue opportunities.

### Improve Customer Experience
**Evidence:** Average rating is **3.80/5** and complaint rate is **6.41%**.

Analyze complaints against delays, route reliability, bus quality, and booking experience.

---

## Limitations

- Dataset is **synthetic** and covers only **2024**.
- Raw data contains intentional quality issues.
- Pearson correlation returned `NaN` due to missing values.
- ANOVA showed unequal variances; Welch ANOVA and post-hoc tests could strengthen the analysis.
- City vs trip-status chi-square was not statistically significant.
- No geographic coordinates were available for route mapping.
- Correlation and association do not establish causation.

## Key Insights

- 🚌 **Mumbai & Pune** show high trip volume and net revenue
- 💰 **Premium AC** has the highest average fare
- 📉 **22.06%** cancellation rate indicates booking leakage
- 🪑 Average occupancy is **57.86%**, leaving capacity headroom
- ⏱️ On-time performance is **68.75%**
- ⭐ Average customer rating is **3.80/5**

---

## Tools Used

- **Kaggle** → Data analysis and notebook environment
- **Python** → Data cleaning, EDA & statistical analysis
- **Excel** → Cleaned data handling & validation
- **Looker Studio** → Interactive dashboards
- **GitHub** → Version control & project sharing

---

## How to Use

1. Clone the repository
2. Install dependencies using `requirements.txt`
3. Open `Data Analysis/cityflo-data-analysis.ipynb`
4. Run the notebook to reproduce the analysis
5. View the dashboard JPGs or open the live Data Studio dashboard

---

## Author

**Pallabi Biswas**  
- B.Tech CSE
- **Contact:** pallabibiswas4002@gmail.com
- **GitHub:** [Palla04](https://github.com/Palla04)
- **LinkedIn:** [Pallabi Biswas](https://www.linkedin.com/in/pallabi-biswas-26151a255/)

---
