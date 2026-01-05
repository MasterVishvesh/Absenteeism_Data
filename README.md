📊 Employee Absenteeism Prediction Project
📌 Project Overview

Employee absenteeism has a direct impact on productivity, workforce planning, and operational costs.
This project focuses on building a machine learning model to predict employee absenteeism levels using historical workplace and personal data.

Rather than treating absenteeism purely as a numeric problem, this project approaches it as a classification task, enabling organizations to proactively identify employees at risk of low, medium, or high absenteeism and take preventive action.

The project is designed as an end-to-end data science workflow, emphasizing not just model building, but also data understanding, preprocessing, evaluation, and explainability.

🎯 Problem Statement

Predict Employee Absenteeism Level based on demographic, health, and work-related factors.

The objective is to classify employees into absenteeism categories (Low / Medium / High) using supervised machine learning techniques.

🧠 Why This Problem Matters

Absenteeism is not random. It is influenced by:

Health conditions, Workload, Distance to work, Age and service time, etc.

📁 Dataset Description
The dataset contains employee-level information such as:
Age, BMI, and service time
Distance from residence to work
Reason for absence
Absenteeism time in hours
Month and weekday information
The target variable was derived from Absenteeism time in hours and converted into meaningful absenteeism levels.

🔍 Exploratory Data Analysis (EDA)
EDA was performed to understand:
Distribution of features
Presence of skewness and extreme values
Central tendency using mean and median
Logical consistency of values
Relationships between variables using correlation analysis

Key observations:
Absenteeism hours are heavily right-skewed
Some features contain valid but extreme values
Correlation captures only linear relationships, requiring non-linear models later

🧹 Data Preprocessing

Preprocessing steps included:
Handling skewed distributions
Converting target variable into categorical classes
Encoding categorical variables using One-Hot Encoding
Scaling numerical features using StandardScaler
Ensuring no data leakage between training and test sets

Why these steps matter:
Models cannot interpret raw categorical text
Scaling ensures fair contribution of all features
Proper preprocessing improves model stability and performance

🤖 Modeling Approach
Baseline Model – Logistic Regression Logistic Regression was chosen as the first model because it:
Is interpretable Provides a strong baseline that helps understand linear relationships. Is computationally efficient. This step establishes a reference point for performance.

Improved Model – Random Forest Classifier
To capture non-linear relationships and feature interactions, a Random Forest Classifier was used.

Why Random Forest:
Handles non-linearity naturally robust to outliers and skewed data Works well with mixed feature types Provides feature importance for explainability

Key parameters:
n_estimators=200 for stable ensemble learning
class_weight='balanced' to handle class imbalance
Fixed random_state for reproducibility

📊 Model Evaluation
Models were evaluated using:
Accuracy
Precision
Recall
F1-score

Confusion Matrix
Special focus was placed on recall for high absenteeism, as missing high-risk employees is more costly than false positives.
The Random Forest model showed improved performance over Logistic Regression, particularly in identifying high absenteeism cases.

🔎 Feature Importance & Interpretability
Random Forest feature importance analysis helped identify key drivers of absenteeism, such as:
Distance to work
Reason for absence
BMI and age-related factors

This adds transparency and makes the model suitable for real-world HR applications.

🧪 Reproducibility & Stability
The project ensures:
Fixed train-test split using random_state
Deterministic model behavior
Consistent evaluation results across runs
Retraining the same model on unchanged data produces identical results, which is expected and desirable for reliable experimentation.

🚀 Technologies Used
Python
Google Colab
Pandas, NumPy
Matplotlib, Seaborn
Scikit-learn

📌 Key Learnings
Correlation captures only linear relationships
Tree-based models handle non-linearity better
Data understanding is as important as model choice
Retraining does not improve a model unless something changes
Explainability builds trust in ML systems

🔮 Future Enhancements

Possible next steps include:
Hyperparameter tuning using GridSearchCV
Cross-validation for robust evaluation
Probability-based risk scoring

Deployment using FastAPI

Integration into HR analytics dashboards
