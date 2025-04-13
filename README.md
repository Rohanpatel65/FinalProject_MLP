# AIDI 1002 Final Project Report

## Group Members
- Jay Patel (200590967)  
- Rohan Patel (200590360)

---

## How to Run

1. Clone this repository or download the notebook directly  
2. Make sure Python, NumPy, Matplotlib, Seaborn, and scikit-learn are installed  
3. Open `main.ipynb` in Jupyter Notebook, VS Code, or Google Colab  
4. Ensure you have access to the dataset (`owid-covid-data.csv`)  
5. Run all cells in order  
6. Analyze the results and compare model performance across continents  

---

## Introduction

This project reproduces and extends the methodology from the GitHub project [COVID19-Algeria-and-World-Dataset](https://github.com/SamBelkacem/COVID19-Algeria-and-World-Dataset) and associated [research paper](https://paperswithcode.com/paper/covid-19-data-analysis-and-forecasting).  
We use a global COVID-19 dataset to understand and model pandemic trends across different continents using machine learning models.

---

## Objective

1. **Reproduce** baseline models to predict total COVID-19 cases  
2. **Contribute** significantly by:
   - Applying the methodology at the **continent level**
   - Comparing performance of:
     - Linear Regression
     - Random Forest Regressor
     - Multi-layer Perceptron (MLP)
   - Introducing MLP as an additional model not explored in the original paper

---

## Dataset Description

- **Source**: [OWID COVID-19 dataset](https://ourworldindata.org/explorers/covid)
- **File Used**: `owid-covid-data.csv`
- **Important Features**:
  - `new_cases`, `new_deaths`, `icu_patients`, `hosp_patients`, `positive_rate`, `people_fully_vaccinated`, `total_tests`
- **Target Variable**:
  - `total_cases`

---

## Exploratory Data Analysis (EDA)

### Feature Distribution

Histograms were generated for key features to understand their spread and detect any outliers or skewness.

### Correlation Heatmap

A heatmap using the latest available data per country was generated to show correlations between variables. Strong relationships were found between `new_cases`, `positive_rate`, and `total_cases`.

### Total Cases/Deaths Over Time

Time series line plots were created for `total_cases` and `total_deaths`, grouped by continent, showing how the pandemic evolved over time across regions.

---

## Modeling and Evaluation

### Approach

We trained the following regression models per continent to predict `total_cases`:
- **Linear Regression** (baseline)
- **Random Forest Regressor** (handles non-linearity and feature interactions)
- **MLP Regressor** (neural network for modeling complex patterns)

### Model Configuration

- Train-test split: 80/20  
- Random seed: 42  
- MLP settings: hidden layers (64, 32), max_iter=300, solver=adam  
- Random Forest: default parameters  

---

### RMSE Comparison Table

| Continent       | Linear Regression RMSE | Random Forest RMSE | MLP RMSE        |
|-----------------|------------------------|---------------------|------------------|
| Africa          | 4.33e+05               | 5.93e+04            | 4.57e+05         |
| Asia            | 7.47e+06               | 4.96e+06            | 7.74e+06         |
| Europe          | 3.72e+06               | 5.60e+05            | 3.95e+06         |
| North America   | 4.77e+06               | 3.45e+06            | 4.86e+06         |
| Oceania         | 1.54e+06               | 1.34e+05            | 1.60e+06         |
| South America   | 7.11e+06               | 5.42e+05            | 7.97e+06         |

---

### Feature Importance (Random Forest)

The Random Forest model also provided feature importance, helping identify `new_cases` and `positive_rate` as the most influential predictors of `total_cases`.

---

## Visualization: RMSE Bar Chart

A bar plot was generated to visually compare RMSE values across continents and models. The Random Forest model generally had the lowest RMSE in each region, confirming its strength in handling complex patterns.

---

## Conclusion

- We successfully **replicated** the modeling approach from the referenced paper.
- We **extended** the methodology to analyze data **per continent**, offering deeper regional insights.
- The **Random Forest** model outperformed others in most regions.
- **MLP Regressor** was introduced as a novel contribution to the original methodology.
- `new_cases` and `positive_rate` were consistently among the most important features.

---


## References

- [OWID COVID-19 Dataset](https://ourworldindata.org/explorers/covid)  
- [Research Paper: COVID-19 Data Analysis and Forecasting](https://paperswithcode.com/paper/covid-19-data-analysis-and-forecasting)  
- [GitHub Repo: COVID19-Algeria-and-World-Dataset](https://github.com/SamBelkacem/COVID19-Algeria-and-World-Dataset)
