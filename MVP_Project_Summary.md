# Crash Severity Prediction Using FARS Data

## Business Problem

Road traffic accidents remain a major public safety concern, resulting in significant fatalities and economic losses. While many safety systems exist, there is still a need to better understand the conditions that lead to high-severity crashes. Crash severity is influenced by a combination of driver behavior, environmental conditions, and roadway characteristics, making it difficult to identify high-risk scenarios using traditional methods.

This project addresses the challenge of predicting crash severity using a data-driven approach. By identifying patterns associated with high-severity crashes, the model can support efforts to reduce fatalities and improve road safety.

## Stakeholders

- **Automotive manufacturers** → Improve Advanced Driver Assistance Systems (ADAS)
- **Insurance companies** → Enhance risk-based pricing and claims prediction
- **Government agencies** → Inform road safety policies and infrastructure planning
- **Fleet operators** → Monitor and mitigate driver risk

## Objectives

- Develop a machine learning model to predict high-severity crashes
- Identify key factors contributing to crash severity
- Provide actionable insights for improving road safety
- Demonstrate an end-to-end data science workflow

## Dataset

The dataset used in this project is the Fatality Analysis Reporting System (FARS) provided by the National Highway Traffic Safety Administration.

The analysis combines three datasets:

- **ACCIDENT** (crash-level information)
- **VEHICLE** (vehicle-level information)
- **PERSON** (driver/person-level information)

**Key Variables:**
- **Crash conditions:** weather, lighting, time of day
- **Road characteristics:** functional road classification
- **Vehicle behavior:** travel speed, speeding involvement
- **Driver attributes:** age, gender, drug involvement

A binary target variable (high_severity) was created from the number of fatalities.

## Methodology

The project follows a structured data science workflow:

### Data Preparation

- Merged datasets using a unique crash identifier (ST_CASE)
- Replaced coded missing values with NaN
- Applied imputation for missing values
- Encoded categorical variables using one-hot encoding
- Scaled numerical variables

### Modeling

Three models were developed and compared:

- Logistic Regression (baseline)
- Random Forest Classifier
- Gradient Boosting Classifier

### Evaluation

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC

Hyperparameter tuning was performed using RandomizedSearchCV for the Random Forest model.

## Results

The Random Forest model achieved the best performance:

- **Accuracy:** ~91%
- **Precision:** ~87%
- **Recall:** ~71%
- **F1-score:** ~0.78

The model demonstrated strong ability to correctly identify high-severity crashes, with relatively low false positives.

## Analysis & Discussion

Feature importance analysis revealed that the most influential variables were:

- **Driver age**
- **Time of crash (hour)**
- **Speed-related variables (travel speed and speed limit)**
- **Weather and road conditions**

Exploratory analysis showed that:

- Younger drivers were more frequently associated with higher-severity crashes
- Higher speeds and certain environmental conditions increased crash severity risk

The model performs well overall, but the recall indicates that some high-risk crashes are still missed. In safety-critical applications, improving recall would be an important next step.

## Conclusions

This project demonstrates that machine learning can effectively identify patterns associated with crash severity using real-world data. The Random Forest model provided strong predictive performance and valuable insights into key risk factors.

The findings highlight the importance of driver behavior, speed, and environmental conditions in determining crash outcomes. These insights can support efforts to improve road safety and inform decision-making for various stakeholders.

##  Future Work

- Improve recall through threshold tuning or alternative models
- Incorporate additional datasets for broader crash coverage
- Apply advanced techniques such as SMOTE to address class imbalance
- Explore model interpretability tools (e.g., SHAP values)
- Extend analysis to predict crash occurrence, not just severity
