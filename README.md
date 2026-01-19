# XGBoost Classification Model - Airline Passenger Satisfaction Analysis

## 📌 Project Overview

This project applies the XGBoost algorithm to classify airline passenger satisfaction using the `Invistico Airline` dataset. The implementation includes  data preprocessing, model training, hyperparameter tuning, and evaluation to identify key factors influencing passenger satisfaction.

## 📊 Dataset

**File:** `Invistico_Airline.csv`

- **Rows:** 129,880

- **Features:** 21 predictor variables + 1 target variable (`satisfaction`)

- **Target:** Binary classification (`satisfied` vs `dissatisfied`)

### Key Features Include:

- Demographic information (Age, Customer Type, Class)

- Flight details (Flight Distance, Type of Travel, Departure/Arrival Delays)

- Service ratings (Seat comfort, Food and drink, Inflight services, Cleanliness, etc.)

## 🏗️ Project Structure

### 1. **Data Preparation**

- Loaded and explored dataset structure

- Identified categorical variables requiring encoding

- Applied one-hot  encoding to: `satisfaction`, `Customer Type`, `Type of Travel`, `Class`

- Split data into training (75%) and testing (25%) sets

### 2. **Model Building**

- Implemented XGBoost Classifier with binary logistic objective

- Performed hyperparameter tuning using GridSearchCV with 5-fold cross-validation

### 3. **Hyperparameter Grid**

```
cv_params = {
    'max_depth': [4],
    'min_child_weight': [3, 5],
    'learning_rate': [0.1, 0.2],
    'n_estimators': [5, 10],
    'subsample': [0.7],
    'colsample_bytree': [0.7]
}
```

### 4. **Model Evaluation Metrics**

- Accuracy

- Precision

- Recall

- F1-Score (used as primary metric for refitting)

## 📈 Results

### Optimal Hyperparameters

```
{
    'colsample_bytree': 0.7,
    'learning_rate': 0.2,
    'max_depth': 4,
    'min_child_weight': 5,
    'n_estimators': 10,
    'subsample': 0.7
}
```

### Model Performance

- **Accuracy:** 89.58%

- **Precision:** 90.03%

- **Recall:** 91.15%

- **F1-Score:** 91.15%

### Confusion Matrix

The model demonstrates strong predictive power with:

- High true positive and true negative rates

- Low false positive and false negative rates

## 🔍 Feature Importance

The project includes visualization of feature importance using XGBoost's built-in functionality, identifying which factors most significantly impact passenger satisfaction.

## 🎯 Key Insights

1. **Model Performance:** The XGBoost model achieved excellent results with F1-score >91%, indicating strong predictive capability for passenger satisfaction.

2. **Business Implications:** The model can help airlines identify critical service areas needing improvement to enhance passenger satisfaction.

3. **Feature Analysis:** Service-related features appear to be significant predictors of satisfaction, though specific importance rankings are visualized in the notebook.