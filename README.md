# 🛵 Micro-Mobility Demand Optimization: A Statistical Analysis of Yulu

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

## 📌 Project Architecture & Objective
This repository contains a deep technical engineering analysis of the factors influencing the demand for shared electric cycles in the Indian micro-mobility market. 

The primary objective is to transition from reactive operational management to proactive, data-driven fleet logistics. By proving statistical significance across environmental and temporal variables, this project establishes a foundational data pipeline suitable for future predictive machine learning models.

---

## 🔬 Statistical Methodology & Hypothesis Testing

The analysis relies on rigorous parametric and non-parametric testing to evaluate operational dependencies.

### 1. Temporal Demand Shift (2-Sample Independent T-Test)
Evaluating if commuter behavior drastically alters fleet utilization between working days and weekends.

* **Null Hypothesis ($H_0$):** There is no significant difference in average demand.
    $$H_0: \mu_{\text{workingday}} = \mu_{\text{weekend}}$$
* **Alternate Hypothesis ($H_1$):** There is a significant difference in average demand.
    $$H_1: \mu_{\text{workingday}} \neq \mu_{\text{weekend}}$$
* **Significance Level:** $\alpha = 0.05$

### 2. Seasonal Demand Volatility (One-Way ANOVA)
Determining if distinct seasons act as primary drivers for macro-level rental volume changes.

* **Null Hypothesis ($H_0$):** Mean demand is consistent across all four seasons.
    $$H_0: \mu_{\text{spring}} = \mu_{\text{summer}} = \mu_{\text{fall}} = \mu_{\text{winter}}$$
* **Alternate Hypothesis ($H_1$):** At least one season exhibits a statistically different mean demand.
* **Assumption Validation:** Levene’s Test applied for homogeneity of variances prior to F-statistic computation.

### 3. Environmental Dependency (Chi-Square Test of Independence)
Testing the categorical dependency between seasonal shifts and specific weather conditions.

* **Null Hypothesis ($H_0$):** Weather conditions are completely independent of the season.
* **Alternate Hypothesis ($H_1$):** Weather conditions are dependent on the season.
* **Test Statistic:**
    $$\chi^2 = \sum \frac{(O_i - E_i)^2}{E_i}$$

---

## 📊 Core Engineering Insights

* **Multicollinearity Identified:** A high positive correlation (Pearson's $r \approx 0.98$) was detected between `temp` and `atemp`. To optimize computational efficiency and model stability in future MLOps pipelines, `atemp` is recommended for feature dropping.
* **The Day-Type Illusion:** The temporal T-test yielded a $p\text{-value} > 0.05$. Aggregate rental volume does not significantly drop on weekends, indicating the need for spatial fleet redistribution (e.g., from tech parks to public squares) rather than absolute fleet reduction.
* **Thermal Sensitivity:** One-Sample T-tests ($H_0: \mu = 25^{\circ}C$) confirmed that high-demand cohorts operate on a distinct thermal profile. Temperature is a proven operational trigger.

---

## 🛠️ Repository Structure

* `notebooks/` : Contains the core Jupyter Notebook with integrated visual EDA and statistical computations.
* `data/` : Dataset schemas and descriptive dictionaries (Note: Raw Yulu data excluded to comply with public hosting standards).
* `exports/` : PDF reports and executive summaries.

---

*Authored for the exploration of production-grade Data Science and ML Engineering.*