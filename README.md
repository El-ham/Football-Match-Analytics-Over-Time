# Data Processing and Machine Learning for Sports Prediction

## Overview
This project involves **data cleaning, preparation, and machine learning modeling** for sports data analysis and prediction. The workflow includes:
- **Data Cleaning:** Merging datasets, handling missing values, and formatting data.
- **Feature Engineering:** Creating new features and aggregating statistical information.
- **Data Preparation:** Feature selection, transformation, and encoding.
- **Machine Learning Modeling:** Training and evaluating different models for prediction.

## Directory Structure
- **Data Cleaningg.ipynb** - Prepares raw data by merging, cleaning, and handling missing values.
- **Date Preparation.ipynb** - Further data transformations and encoding for modeling.
- **Model - Original.ipynb** - Training machine learning models for prediction.

---

## Data Cleaning
### **Techniques Used:**
- Merging multiple CSV files from a directory.
- Handling missing values by:
  - Using grouped transformations based on teams.
  - Dropping unnecessary columns such as metadata or redundant identifiers.
- Resetting index and formatting column names.
- Encoding categorical variables using **One-Hot Encoding** to convert team names, referees, and other categorical data into numerical form.

---

## Feature Engineering
Feature engineering is a key step in improving predictive accuracy. Several new features were created based on historical data:

### **Rolling Statistics:**
- **Rolling Mean, Sum, and Median:** These statistics were calculated over a **6-game window** for both home and away teams.
- Helps in understanding team performance trends over recent games.

### **Performance Aggregation:**
- Aggregating past game statistics, such as:
  - **Average Goals Scored** (Home & Away)
  - **Shots on Target**
  - **Possession Percentage**
  - **Defensive Stats (Tackles, Saves, Fouls)**
- Provides a broader picture of team consistency.

### **Time-Based Features:**
- **Days Since Last Match:** Measures the gap between games to assess fatigue or recovery.
- **Game Time Feature:** Captures differences in performance between afternoon and evening matches.

### **Odds & Betting Data:**
- Extracted betting odds from different bookmakers.
- Converted them into probability distributions to identify trends in betting markets.

### **Imputation Strategies:**
- Missing values for aggregated statistics were filled using:
  - Mean values for teams over the season.
  - Team-based rolling averages for recent performance.
  - Combined home & away team statistics for better accuracy.

---

## Data Preparation
### **Steps Performed:**
- Loading and transforming the cleaned dataset.
- Removing redundant or highly correlated features to reduce dimensionality.
- Encoding categorical variables into numerical formats for model compatibility.
- Standardizing numerical features where necessary.

---

## Machine Learning Models
Different models were tested for predicting match outcomes:

### **1. Decision Tree Classifier**
- Used for initial exploration of key features.
- Helps in understanding the most significant factors influencing game outcomes.

### **2. Random Forest Classifier**
- Provides improved predictive accuracy by using multiple decision trees.
- Evaluates the importance of different features in predicting results.

### **3. XGBoost Classifier**
- Advanced gradient boosting method.
- Fine-tuned using grid search for optimal hyperparameters.
- Provides high accuracy and handles imbalanced datasets efficiently.

---

## Model Evaluation
- **Confusion Matrix:** Used to analyze the classification performance.
- **Feature Importance Analysis:** Identifies the most influential features in determining match outcomes.
- **Hyperparameter Tuning:** Performed via grid search to optimize model performance.

---

## Dependencies
This project requires the following Python libraries:
- `pandas` (for data handling)
- `numpy` (for numerical operations)
- `matplotlib` (for visualization)
- `sklearn` (for machine learning models)
- `xgboost` (for advanced boosting models)
- `statsmodels` (for statistical analysis)

---

## Conclusion
This project successfully processes raw sports data and applies machine learning models to predict match outcomes. The feature engineering techniques significantly improve model performance by incorporating historical team statistics, betting odds, and time-based trends.

Future improvements could include:
- **Deep learning models** for better pattern recognition.
- **Additional contextual features** such as weather conditions or player injuries.
- **Further tuning of hyperparameters** for increased accuracy.

