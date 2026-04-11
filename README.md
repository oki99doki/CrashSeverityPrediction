# Crash Severity Prediction using FARS Data
This project aims to predict the likelihood of high-severity crashes based on environmental, driver, and roadway factors.

## 1. Business Problem Scenario
The Goal is to perform comprehensive data analysis on real-world traffic accident data. This includes:

- Data cleaning
- Exploratory data analysis (EDA)
- Statistical analysis

### Problem Statement
Road traffic accidents result in significant fatalities and economic losses each year. While Advanced Driver Assistance Systems (ADAS) aim to reduce crash severity, many systems lack data-driven risk prediction based on real-world conditions.

This project aims to predict the likelihood of high-severity crashes based on environmental, driver, and roadway factors.

### Stakeholders
- Automotive companies → improve ADAS systems
- Insurance companies → risk-based pricing
- Government agencies → road safety policy decisions
- Fleet operators → driver risk monitoring

### Business Goals
- Identify key factors contributing to fatal crashes
- Enable proactive safety interventions
- Improve risk awareness in driving environments
- Support data-driven ADAS enhancements

### Why Machine Learning?
- Identify key factors contributing to fatal crashes
- Enable proactive safety interventions
- Improve risk awareness in driving environments
- Support data-driven ADAS enhancements

## 2. Dataset Description

### Source
National Highway Traffic Safety Administration
[FARS dataset](https://www.nhtsa.gov/es/research-data/fatality-analysis-reporting-system-fars)


### Size
- ~30,000–40,000 crashes per year
- Multi-year dataset: 100K–300K+ records

### Key Variables
- Crash: FATALS, HOUR, WEATHER, LGT_COND, FUNC_SYS
- Vehicle: SPEEDREL, TRAV_SP, VSPD_LIM
- Driver: AGE, SEX, DRUGS

### Relevance to Business Problem
- Contains real-world fatal crash data
- Captures environmental + human + vehicle factors
- Directly supports risk prediction modeling

## 3. Success Criteria

### Technical Metrics
- Accuracy
- Precision / Recall
- F1-score
- ROC-AUC

### Business Metrics
- Ability to identify high-risk conditions
- Interpretability of key risk factors
- Actionable insights for ADAS and policy decisions

## 4. Problem-Solving Process

### Data Acquisition & Understanding

#### Approach:
- Download FARS data (ACCIDENT, VEHICLE, PERSON tables)
- Merge using ST_CASE

#### Data Quality Plan:
- Identify missing values (coded as 99, 998, etc.)
- Check inconsistencies across tables

#### Visualization:
- Distribution plots (age, speed, time)
- Correlation heatmaps
- Crash frequency by conditions


### Data Preparation & Feature Engineering

#### Cleaning:
- Replace coded missing values → NaN
- Impute using median/mode

#### Feature Engineering:
- Binary target: high severity (FATALS > 1)
- Time-based features (e.g., night driving)
- Weather grouping (clear vs adverse)

#### Pipeline:
- Use scikit-learn Pipeline + ColumnTransformer
- Include:
  - Imputation
  - Scaling
  - Encoding

### Modeling Strategy

#### Algorithms (minimum 3):
1. Logistic Regression (baseline)
2. Random Forest (nonlinear model)
3. Gradient Boosting (e.g., XGBoost)

#### Cross-Validation:
- Stratified K-Fold (e.g., k=5)

#### Hyperparameter Tuning:
- GridSearchCV / RandomizedSearchCV

#### Evaluation Metrics:
- F1-score → balances precision & recall
- ROC-AUC → model discrimination
- Recall → important for identifying high-risk crashes

## 5. Results Interpretation & Communication

### Insights Translation
- Identify top risk factors:
  - Speeding
  - Night driving
  - Weather conditions

Translate into: “Crashes at night with high speed limits have X% higher fatality risk.”

### Visualization Plan
- Feature importance charts
- ROC curves
- Confusion matrix
- Risk factor bar charts

### Communication Strategy
- Use simple language:
  - “High-risk conditions” instead of probabilities
  - Focus on impact, not algorithms
 

## 6. Conceptual Flow

### Pipeline Flow
![Flowchart of Pipeline](Screenshot.png)

### Dependencies
- Clean data → required for modeling
- Feature engineering → improves performance
- Model evaluation → drives business insights

## 7. Project Timeline

### Dataset Finalization & Problem Formulation — 2 days (April 14)
- Define problem
- Select variables
- Set up repository

### Exploratory Data Analysis — 3 days (April 17)
- Data profiling
- Visualizations
- Insight documentation

### Data Preprocessing — 3 days (April 21)
- Cleaning
- Feature engineering
- Pipeline setup

### Model Development — 3 days (April 24)
- Baseline models
- Model comparison
- Hyperparameter tuning

### Model Evaluation & Refinement — 3 days (April 28)
- Final model selection
- Performance evaluation
- Business interpretation

### Documentation & Reporting — 2 days (April 30)
- Technical report
- Visualizations
- Presentation slides

### Final Review & Submission — 2 days (May 2)
- QA checks
- Video recording
- Submission

## 8. Potential Challenges

### Data Challenges
- Missing values (coded numerically)
- Schema inconsistencies across tables

### Modeling Challenges
- Class imbalance (fatal vs non-fatal)
- Feature correlation

### Technical Challenges
- Pipeline debugging (encoding, NaNs)
- Large dataset handling

## Areas for Further Learning
- Advanced feature engineering
- Imbalanced classification techniques (SMOTE)
- Model interpretability (SHAP values)


## Final Value Proposition
This project will:
- Deliver a predictive model for crash severity
- Provide actionable insights for safety systems
- Demonstrate end-to-end data science capability using CRISP-DM

