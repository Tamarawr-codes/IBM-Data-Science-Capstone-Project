# IBM Data Science Professional Certificate Capstone: SpaceX Falcon 9 First Stage Landing Prediction

## Executive Summary
This repository contains the completed capstone project for **Course 10 (Applied Data Science Capstone)** of the IBM Data Science Professional Certificate. 

The primary business objective is to predict whether the SpaceX Falcon 9 first-stage booster will land successfully after launch. Because first-stage reuse saves SpaceX tens of millions of dollars per mission—allowing them to offer launch prices around $62M compared to traditional competitor costs of $165M+—predicting landing success is critical for determining launch costs, evaluating commercial risk, and pricing services competitively.

---

## Project Structure & Data Pipeline

1. **Data Collection:**
   * **REST API:** Extracted historical launch records from the SpaceX API.
   * **Web Scraping:** Scraped Wikipedia launch records using `BeautifulSoup` to capture detailed mission metrics.

2. **Data Wrangling & Processing:**
   * Cleaned dataset missing values, structured outcomes into a binary variable (`1` = Landed, `0` = Failed/Lost), and performed one-hot encoding on categorical variables (`LaunchSite`, `Orbit`).

3. **Exploratory Data Analysis (EDA):**
   * **SQL Analytics:** Queried database records using SQLite to inspect site counts, success ratios, and payload masses.
   * **Visual Analytics:** Built Seaborn/Matplotlib visualizations to evaluate payload mass, flight number, and orbit type correlations.

4. **Interactive Mapping & Dashboards:**
   * **Folium:** Constructed interactive maps with distance poly-lines to analyze proximity between launch sites, coastlines, railways, and highways.
   * **Plotly Dash:** Developed a dynamic dashboard (`app.py`) with drop-down site filters and payload range sliders to visualize real-time landing success distributions.

5. **Predictive Machine Learning:**
   * Trained and tuned multiple binary classification models: **Logistic Regression, Support Vector Machine (SVM), Decision Tree, and K-Nearest Neighbors (KNN)** using `GridSearchCV`.

---

## Key Results & Insights

* **Model Accuracy:** All four classification models achieved a test accuracy of **83.33%**.
* **Optimal Model:** The **Support Vector Machine (SVM)** model with a `sigmoid` kernel ($C=1.0, \gamma=0.0316$) demonstrated robust, consistent performance on test data.
* **Launch Site Dynamics:** `KSC LC-39A` produced the highest overall landing success percentage among all operational pads.
* **Payload & Orbit Trends:** Landing success rates increase significantly with heavier payload masses (3,000 kg – 6,000+ kg) and later booster revisions (Block 4 and Block 5). High-altitude orbits like `ES-L1`, `GEO`, `HEO`, and `SSO` show near-100% success rates.

---

## Repository Contents

```text
├── Data_Collection_API.ipynb
├── Data_Collection_WebScraping.ipynb
├── Data_Wrangling.ipynb
├── EDA_with_SQL.ipynb
├── EDA_with_Visualization.ipynb
├── Interactive_Visual_Analytics_Folium.ipynb
├── Machine_Learning_Prediction.ipynb
├── app.py                     # Plotly Dash Web Application
└── README.md