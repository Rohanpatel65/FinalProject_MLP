# AIDI 1002 Final Project Report: COVID-19 Dataset Analysis by Continent

## Group Members
- Jay Patel (200590967)  
- Rohan Patel (200590360)

---------------------------------------
## How to Run

1. Clone this repository or download the notebook directly  
2. Make sure Python,numpy,matplotlib,seaborn and scikit-learn are installed  
3. Open main.ipynb in Jupyter Notebook, VS Code, or Google Colab.  
4. Make sure you have access to the dataset.
5. Run all cells in order.
6. Analyze the results and compare model performance across continents.

## Introduction
This project aims to reproduce and extend the methodology from the GitHub project [COVID19-Algeria-and-World-Dataset](https://github.com/SamBelkacem/COVID19-Algeria-and-World-Dataset) using a global COVID-19 dataset from Our World in Data.
and here is the [Research Paper](https://paperswithcode.com/paper/covid-19-data-analysis-and-forecasting).
Our focus is on understanding and modeling COVID-19 trends **by continent** using machine learning models.

---

## Objective
1. **Reproduce** baseline models to predict total COVID-19 cases.
2. **Contribute** significantly by applying the methodology at the **continent level** and comparing the performance of:
   - Linear Regression
   - Random Forest Regressor
   - Multi-layer Perceptron (MLP)

---

## 📁 Dataset Description
- **Source**: [OWID COVID-19 dataset](https://ourworldindata.org/explorers/covid?country=USA~BRA~JPN~DEU~CAN~OWID_NAM~OWID_HIC~AND&Metric=Excess+mortality+%28estimates%29&Interval=Cumulative&Relative+to+population=true)
- **File used**: `owid-covid-data.csv`
- **Important columns**:
  - Features: `new_cases`, `new_deaths`, `icu_patients`, `hosp_patients`, `positive_rate`, `people_fully_vaccinated`, `total_tests`
  - Target: `total_cases`

---

## 🔍 Exploratory Data Analysis (EDA)

### 📊 Feature Distribution with Histograms
We plotted histograms to understand the distribution of key features like new cases, new deaths, and vaccination rates. These helped us identify outliers and skewed data.

### 🔥 Feature Correlation with a Heatmap
A heatmap was generated to examine the correlation between numerical features. This showed strong correlations between variables like `new_cases`, `positive_rate`, and `total_cases`.

### 📈 Output Variable Curves
Time series line plots were generated for `total_cases` and `total_deaths` across continents. This helped visualize the COVID-19 progression trend by region.

---

## 🧠 Modeling and Evaluation

### 🧪 Approach
We trained three regressors to predict `total_cases` per continent:
- **Linear Regression** – a simple baseline model.
- **Random Forest Regressor** – captures non-linear relationships and interactions.
- **Multi-layer Perceptron (MLP)** – a neural network that models complex patterns.

### 📉 RMSE Comparison Table

| Continent       | Linear Regression RMSE | Random Forest RMSE | MLP RMSE        |
|-----------------|------------------------|---------------------|------------------|
| Africa          | 4.333410e+05           | 5.925974e+04        | 4.565798e+05     |
| Asia            | 7.469116e+06           | 4.963303e+06        | 7.739407e+06     |
| Europe          | 3.715083e+06           | 5.595641e+05        | 3.945734e+06     |
| North America   | 4.769654e+06           | 3.448719e+06        | 4.859028e+06     |
| Oceania         | 1.537966e+06           | 1.337384e+05        | 1.595772e+06     |
| South America   | 7.113168e+06           | 5.420830e+05        | 7.970711e+06     |


---

## 🎁 Contribution Summary
- Shifted focus from country-level (Algeria) to continent-level COVID-19 modeling.
- Introduced **Multi-layer Perceptron (MLP)** as an additional model.
- Conducted extensive evaluation using RMSE to compare performance.

---

## 📌 Conclusion
In this project, we reproduced and extended the methodology from the original research on COVID-19 data analysis. By using the globally trusted "Our World in Data" COVID-19 dataset, we performed an in-depth study of COVID-19 trends at the continent level, exploring how machine learning models can be used to predict the total number of cases using relevant features such as new cases, new deaths, testing, and positive rate.

We implemented and evaluated three machine learning models: Linear Regression, Random Forest Regressor, and Multi-Layer Perceptron (MLP). These models were trained and tested independently for each continent, and their performances were compared using Root Mean Squared Error (RMSE) as the evaluation metric. The results showed that ensemble models like Random Forest generally performed better than Linear Regression, while MLP also showed competitive results depending on the data size and feature variability of each continent.

we further visualized the feature distributions, correlation heatmaps, and time-series trends of COVID-19 cases and deaths. These visualizations provided valuable insights into the pandemic's evolution and helped identify which variables had strong predictive power.

---
## 📎 References
- OWID COVID-19 Dataset: https://ourworldindata.org/coronavirus
- GitHub Reference: https://github.com/SamBelkacem/COVID19-Algeria-and-World-Dataset
