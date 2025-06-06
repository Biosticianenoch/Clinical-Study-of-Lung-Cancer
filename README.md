# 🫁 Risk Factor Analysis of Lung Cancer

This project investigates the risk factors associated with lung cancer using survey data and robust statistical techniques in R. The goal is to build a predictive model, identify statistically significant risk factors, and make data-driven recommendations for prevention and health policy.

---

## 🎯 Study Objectives

- To explore demographic, behavioral, and clinical variables related to lung cancer.
- To identify statistically significant risk factors using bivariate and multivariate analyses.
- To build and validate a predictive logistic regression model for classifying lung cancer risk.
- To examine possible interactions and mediating effects among predictors.
- To make evidence-based recommendations for public health interventions.

---

## 📁 Dataset Summary

- **Source**: Survey Lung Cancer Dataset
- **Observations**: 309 individuals
- **Variables**: 16 (Demographic, Behavioral, Clinical)
- **Target Variable**: `LUNG_CANCER` (YES/NO)

---

## 🔍 Data Preprocessing

- ✅ Removed duplicates (33 entries)
- ✅ Encoded categorical variables
- ✅ Ensured correct data types
- ✅ No missing values or outliers (except natural variability in age)

---

## 📊 Exploratory Data Analysis (EDA)

- Visualized distribution of each feature (histograms and bar charts)
- Conducted **t-tests** for continuous variables and **Chi-square tests** for categorical associations
- Found a **mean age** of 21 years, indicating a relatively young population

---

## 🔁 Bivariate Analysis Highlights

- Significant associations found with:
  - **Yellow Fingers** (p = 0.003)
  - **Anxiety** (p = 0.026)
  - **Peer Pressure** (p = 0.002)
  - **Chronic Disease** (p = 0.026)
  - **Fatigue** (p = 0.013)
  - **Allergy** (p = 8.05e-08)
  - **Wheezing**, **Coughing**, **Alcohol Consumption**, **Swallowing Difficulty**, **Chest Pain** – all p < 0.05

---

## 🤖 Predictive Modeling

### Logistic Regression (Refined)
- Removed insignificant predictors (Gender, Age, Wheezing, etc.)
- Final model includes 9 significant predictors

### Model Validations
- **Goodness-of-fit**: Passed
- **No multicollinearity**: All VIF < 2.5
- **Uniform residuals**: Confirmed
- **No influential outliers**: Detected

### Performance Metrics
| Metric             | Value   |
|--------------------|---------|
| **Tjur's R²**      | 0.566   |
| **AIC**            | 113.1   |
| **Accuracy**       | 89.7%   |
| **AUC (ROC)**      | 0.963   |

---

## 📈 Significant Predictors & Odds Ratios

| Predictor               | Odds Ratio | 95% CI         | Significance |
|------------------------|------------|----------------|--------------|
| SMOKING                | 0.25       | 0.06 – 0.86    | *            |
| YELLOW_FINGERS         | 0.18       | 0.05 – 0.61    | **           |
| PEER_PRESSURE          | 0.17       | 0.04 – 0.54    | **           |
| CHRONIC_DISEASE        | 0.06       | 0.01 – 0.25    | ***          |
| FATIGUE                | 0.06       | 0.01 – 0.21    | ***          |
| ALLERGY                | 0.19       | 0.04 – 0.78    | *            |
| ALCOHOL_CONSUMING      | 0.17       | 0.04 – 0.67    | *            |
| COUGHING               | 0.05       | 0.01 – 0.25    | ***          |
| SWALLOWING_DIFFICULTY  | 0.03       | 0.00 – 0.20    | ***          |

---

## 🔁 Interaction Effects (Moderation & Mediation)

- 🔄 **Smoking × Age**
- 🔄 **Alcohol Consumption × Gender**
- 🔄 **Fatigue × Chronic Disease**
- 🔄 **Peer Pressure × Anxiety**
- 🔄 **Chronic Disease × Fatigue**

Visualized using interaction plots to understand modification or mediation of relationships.

---

## 🧰 Tools & Libraries

- `tidyverse`, `sjPlot`, `car`, `vip`, `gtsummary`, `effectsize`, `pROC`, `performance`, `equatiomatic`, `emmeans`, `report`, `ggeffects`

---

## ✅ Key Findings

- Fatigue, coughing, and swallowing difficulty are **strong predictors** of lung cancer.
- Behavioral risks such as smoking, alcohol use, and peer pressure are significantly linked to increased cancer risk.
- The logistic regression model provides an excellent classification performance (AUC = 0.96).

---

## 💡 Recommendations

1. **Awareness Campaigns**:
   - Educate the public about behavioral risk factors: smoking, peer pressure, and alcohol use.
   - Highlight symptoms such as chronic fatigue, coughing, and swallowing difficulty.

2. **Screening and Early Detection**:
   - Regular health checks for individuals showing multiple symptoms or risk factors.
   - Promote community-based screening especially among youth and smokers.

3. **Policy and Prevention**:
   - Implement tobacco and alcohol control policies.
   - Encourage psychological counseling to address anxiety and peer influence.

4. **Further Research**:
   - Explore longitudinal data for causality.
   - Integrate genetic markers and environmental exposures in future studies.

---

## 🚀 How to Run This Project

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/lung-cancer-risk-analysis.git
   cd lung-cancer-risk-analysis
