# 🛵 Micro-Mobility Demand Optimization
## Statistical Analysis of Yulu Bike Demand

<p align="center">
    <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
    <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy" />
    <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas" />
    <img src="https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white" alt="SciPy" />
    <img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white" alt="Matplotlib" />
</p>

<p align="center">
    Data-driven hypothesis testing to understand what truly drives electric cycle demand in the Indian micro-mobility market.
</p>

---

## 📌 Project Objective

This repository presents a technical statistical analysis of the variables influencing shared electric cycle demand for Yulu.

The goal is to move from reactive operational decisions to proactive, evidence-based fleet planning. By validating significance across temporal and environmental factors, this project builds a foundation for future predictive modeling and demand forecasting.

---

## 🔎 What This Analysis Covers

- Exploratory data analysis of rental demand behavior
- Statistical significance testing across time and seasonality
- Environmental dependency checks between weather and season
- Actionable business insights for fleet operations

---

## 🔬 Statistical Methodology

### 1. Temporal Demand Shift (2-Sample Independent T-Test)

Checks whether demand differs significantly between working days and weekends.

- Null Hypothesis ($H_0$): No significant difference in mean demand
    $$H_0: \mu_{\text{workingday}} = \mu_{\text{weekend}}$$
- Alternate Hypothesis ($H_1$): Significant difference in mean demand
    $$H_1: \mu_{\text{workingday}} \neq \mu_{\text{weekend}}$$
- Significance level: $\alpha = 0.05$

### 2. Seasonal Demand Volatility (One-Way ANOVA)

Tests whether demand means vary significantly across seasons.

- Null Hypothesis ($H_0$):
    $$H_0: \mu_{\text{spring}} = \mu_{\text{summer}} = \mu_{\text{fall}} = \mu_{\text{winter}}$$
- Alternate Hypothesis ($H_1$): At least one seasonal mean differs
- Assumption check: Levene's Test for homogeneity of variances

### 3. Environmental Dependency (Chi-Square Test of Independence)

Evaluates whether weather condition and season are statistically dependent.

- Null Hypothesis ($H_0$): Weather and season are independent
- Alternate Hypothesis ($H_1$): Weather and season are dependent
- Test statistic:
    $$\chi^2 = \sum \frac{(O_i - E_i)^2}{E_i}$$

---

## 📊 Key Insights

- Multicollinearity detected: Strong correlation (Pearson's $r \approx 0.98$) between `temp` and `atemp`; dropping one feature (typically `atemp`) is recommended for model stability.
- Weekend demand myth: T-test returned $p\text{-value} > 0.05$, suggesting overall volume does not significantly fall on weekends.
- Temperature sensitivity: One-sample tests around $H_0: \mu = 25^{\circ}C$ indicate high-demand cohorts have a distinct thermal profile.

---

## 🗂️ Repository Structure

- `notebooks/` - Core Jupyter notebook with EDA, statistical tests, and interpretation
- `data/` - Source data and supporting input files
- `exports/` - Final report artifacts and summaries

---

## 🚀 How to Run

1. Open `notebooks/index.ipynb`
2. Ensure required Python libraries are installed (`numpy`, `pandas`, `scipy`, `matplotlib`)
3. Run cells in order to reproduce analysis and outputs

---

*Built to practice production-minded Data Science and statistical reasoning.*