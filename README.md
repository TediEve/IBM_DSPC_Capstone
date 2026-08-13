# 🚀 SpaceX Falcon 9 First Stage Landing Prediction
> **IBM Data Science Professional Certificate — Capstone Project**

---

## 📌 Project Overview
Space X advertises Falcon 9 rocket launches on its website with a cost of **62 million dollars**; other providers cost upward of **165 million dollars** each, much of the savings is because Space X can reuse the first stage. 
The goal of this project is to predict if the first stage will land, so we can determine the cost of a launch. This can help a competitive company to make more informed bids against SpaceX for a rocket launch.

---

## 🛠️ Tech Stack & Dependencies
* **Programming Language:** Python 3.x
* **Data Manipulation & Analysis:** `pandas`, `numpy`
* **Database & Querying:** `sqlite3`, SQL queries
* **Visualization & Mapping:** `matplotlib`, `seaborn`, `folium`
* **Interactive Dashboard:** `dash`, `plotly`
* **Machine Learning:** `scikit-learn`

---

## 📊 Project Methodology Workflow

```text
[1. Data Collection] ➔ [2. Data Wrangling] ➔ [3. Exploratory Data Analysis] ➔ [4. Interactive Analytics] ➔ [5. Predictive Modeling]
     (API & Scraping)        (One-Hot Encoding)         (SQL & Visualizations)          (Folium & Dash)         (GridSearch Tuning)
```
1. **Data Collection:** Gathered historical launch data using SpaceX REST API endpoints and web scraping via `BeautifulSoup`. *(Note: Due to temporary SpaceX REST API downtime during development, the standardized IBM Coursera backup dataset was used to ensure pipeline continuity).*
2. **Data Wrangling:** Filtered Falcon 9 records, imputed missing values (e.g., payload mass averages), and created the target binary classification column (1 = successful landing, 0 = failed landing).
3. **Exploratory Data Analysis (EDA):** Evaluated flight numbers, payload mass, orbit types, and launch site success rates using SQL queries and statistical plots.
4. **Interactive Visual Analytics:**
   *Folium:* Mapped launch sites, launch trajectories, proximity to coastlines, highways, airports, railroads and so on.
   *Plotly Dash:* Constructed an interactive dashboard featuring dropdown for site selections and a slider for choosing payload range to dynamically inspect success rates.
5. **Predictive Analytics (Machine Learning):** Standardized input features using StandardScaler and tuned hyperparameters across 4 classification models using GridSearchCV with 10-fold cross-validation.
### 📈 Machine Learning Results Summary

The performance of four classification models was evaluated on the test set ($N=18$):

| Model | Best CV Score | Test Accuracy |
| :--- | :---: | :---: |
| **K-Nearest Neighbors (KNN)** | **0.8482** | **83.33%** |
| **Logistic Regression** | 0.8214 | 83.33% | 
| **Support Vector Machine (SVM)** | 0.8214 | 83.33% |
| **Decision Tree** | 0.8036 | 83.33% |
**Conclusion:** While KNN, Logistic Regression, and SVM achieved identical test accuracies (83.33%) due to the small test sample size ($N=18$), KNN was selected as the winner due to achieving the highest cross-validation score during Grid Search and being the simplest one

---

## 💻 How to Run It

### 1. Clone this repo

```bash
git clone [https://github.com/](https://github.com/)TediEve/IBM_DSPC_Capstone.git
cd IBM_DSPC_Capstone
```
### 2. Set up virtual environment
```bash
python -m venv venv

# On Mac/Linux:
source venv/bin/activate  

# On Windows:
venv\Scripts\activate
```
### 3. Install the needed libraries(*Note:* The provided notebooks include package installation cells which can be skipped if running locally)
```bash
pip install pandas numpy matplotlib seaborn scikit-learn dash plotly folium
```
### 4. Run the dashboard
```bash
python dash_app/spacex_dash_app.py
```
---

## 📜 License & Acknowledgments

* **License:** Distributed under the [MIT License](LICENSE). See `LICENSE` for more information.
* **Course:** IBM Data Science Professional Certificate on Coursera.
* **Data Source:** SpaceX REST API & Wikipedia.
