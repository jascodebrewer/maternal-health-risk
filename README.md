# Maternal Health Risk Prediction

## Overview
This project aims to analyze and predict maternal health risk levels based on various physiological parameters such as age, blood pressure, blood sugar levels, body temperature, and heart rate. The dataset used for this analysis is obtained from the `ucimlrepo` library.

## Dataset
The dataset was fetched from the UCI Machine Learning Repository (ID: 863) using the `ucimlrepo` package. It consists of the following features:

- **Age**: Age of the patient (in years)
- **SystolicBP**: Systolic blood pressure (mmHg)
- **DiastolicBP**: Diastolic blood pressure (mmHg)
- **BS**: Blood sugar level (mmol/L)
- **BodyTemp**: Body temperature (°F)
- **HeartRate**: Heart rate (beats per minute)
- **RiskLevel**: Categorical target variable (Low, Mid, High)

## Installation
To run this project, install the required dependencies:

```bash
pip install ucimlrepo pandas numpy matplotlib seaborn scikit-learn xgboost
```

## Exploratory Data Analysis (EDA)
Several visualizations were performed to understand the dataset:

- Histograms to analyze distributions of numerical features.
- Boxplots to detect outliers.
- Pairplots to explore relationships between features and target classes.
- Heatmaps to study correlations among features.

### Key Findings:
- Age, Blood Sugar (BS), and Blood Pressure (BP) showed significant differences across risk levels.
- Heart Rate and Body Temperature had a weaker correlation with risk level.
- High-risk cases tend to have higher blood pressure and blood sugar levels.
- Some outliers were identified in heart rate and body temperature.

## Model Selection
Three classification models were trained and evaluated:

1. **Logistic Regression (Baseline Model)**
2. **Random Forest Classifier**
3. **XGBoost Classifier**

### Results:
| Model                | Accuracy |
|----------------------|----------|
| Logistic Regression | 64.04%   |
| Random Forest       | 81.28%   |
| XGBoost            | 84.23%   |

XGBoost outperformed other models, with the highest accuracy and balanced precision/recall across all risk levels.

## Hyperparameter Tuning
Grid search was applied to optimize the Random Forest and XGBoost models. After tuning:

- **Random Forest Accuracy**: 81.3%
- **XGBoost Accuracy**: 84.2%

XGBoost remained the best-performing model with improved recall and precision across all risk categories.

## How to Use
To run the notebook and reproduce the results:

1. Install the dependencies using:
   ```bash
   pip install -r requirements.txt
   ```
2. Load and preprocess the dataset.
3. Perform EDA to understand feature distributions.
4. Train and evaluate models.
5. Use the best-performing model (**XGBoost**) for predictions.

