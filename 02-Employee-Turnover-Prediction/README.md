# Employee Turnover Prediction

## Project Overview

This project focuses on predicting employee turnover using Machine Learning. It uses **Logistic Regression** to identify whether an employee is likely to stay with or leave an organization.

The project compares three Logistic Regression approaches:
- Baseline Logistic Regression
- Logistic Regression with L1 Regularization (Lasso)
- Logistic Regression with L2 Regularization (Ridge)

The objective is to evaluate model performance using classification metrics and understand how regularization affects predictions.

## Tools & Technologies

- **Python** – Programming language
- **Pandas & NumPy** – Data manipulation and analysis
- **Matplotlib & Seaborn** – Data visualization
- **Scikit-learn** – Machine Learning, preprocessing and model evaluation
- **Jupyter Notebook** – Development environment

## Project Structure

```text
02-Employee-Turnover-Prediction/
│
├── Employee_Turnover.ipynb
├── employee_turnover.csv
├── requirements.txt
└── README.md
```

## Dataset Information

- **Initial Records:** 1,350
- **Duplicate Records Removed:** 450
- **Final Records:** 900
- **Input Features:** 15
- **Target Variable:** `Employee_Turnover`

### Target Variable

| Value | Meaning |
|---|---|
| 0 | Employee Stayed |
| 1 | Employee Left |

### Features Used

The dataset contains employee-related features such as:

- Job Satisfaction
- Performance Rating
- Years at Company
- Work-Life Balance
- Distance From Home
- Monthly Income
- Education Level
- Age
- Number of Companies Worked
- Employee Role
- Annual Bonus
- Training Hours
- Department
- Annual Bonus Squared
- Annual Bonus–Training Hours Interaction

## Project Workflow

### 1. Data Loading & Exploration
- Loaded the dataset using Pandas.
- Inspected dataset structure and data types.
- Used descriptive statistics to understand feature distributions.
- Examined the target variable distribution.

### 2. Data Cleaning
- Identified 450 duplicate records.
- Removed duplicate rows using `drop_duplicates()`.
- Checked missing values.
- No missing values were found in the cleaned dataset.

### 3. Feature & Target Separation
- Separated 15 input features into `X`.
- Selected `Employee_Turnover` as the target variable `y`.

### 4. Train-Test Split
- Training data: 80% (720 records)
- Testing data: 20% (180 records)
- Used `random_state=42`.
- Applied stratified sampling to preserve class proportions.

### 5. Feature Scaling
Applied `StandardScaler` to standardize the features.

The scaler was fitted on training data and then applied to testing data to avoid data leakage during preprocessing.

### 6. Model Building

Three Logistic Regression models were trained and evaluated.

**Baseline Logistic Regression**
- No regularization penalty.
- Used as the reference model.

**L1 Regularization (Lasso)**
- Uses L1 penalty.
- Can reduce some feature coefficients to zero.
- One feature coefficient became zero in this experiment.

**L2 Regularization (Ridge)**
- Uses L2 penalty.
- Shrinks coefficients while generally retaining all features.

### 7. Model Evaluation

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- Classification Report

## Model Performance

The following results were obtained from the notebook's 180-record test set.

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| Baseline Logistic Regression | **88.33%** | **90.36%** | 85.23% | **87.72%** |
| L1 Regularization | 87.22% | 89.16% | 84.09% | 86.55% |
| L2 Regularization | 87.78% | 89.29% | **85.23%** | 87.21% |

### Best Model

**Baseline Logistic Regression** achieved the highest F1-score of **87.72%** and accuracy of **88.33%** among the three tested configurations.

Therefore, it was selected as the best-performing model in this experiment.

## Visualizations

The Jupyter Notebook includes:

- Employee Turnover Distribution
- Baseline Logistic Regression Confusion Matrix
- L1 Regularization Confusion Matrix
- L2 Regularization Confusion Matrix
- Logistic Regression Model Performance Comparison

## Key Learnings

- Understanding the complete supervised Machine Learning workflow.
- Handling duplicate records and checking missing values.
- Separating input features and target variables.
- Performing stratified train-test splitting.
- Applying feature scaling with StandardScaler.
- Understanding Logistic Regression.
- Comparing L1 and L2 regularization.
- Evaluating classification models using multiple performance metrics.
- Interpreting model coefficients and confusion matrices.

## Limitations

- Model performance was evaluated using a single train-test split.
- Hyperparameter tuning and cross-validation were not performed.
- ROC-AUC evaluation was not included.
- The dataset's original source and real-world representativeness are not documented in the notebook.
- The model has not been deployed as a production application.

## Future Improvements

- Perform cross-validation for more reliable evaluation.
- Apply hyperparameter tuning to improve model performance.
- Evaluate models using ROC-AUC and ROC curves.
- Perform deeper feature importance and coefficient analysis.
- Save the trained model using Joblib.
- Develop an interactive employee turnover prediction application.

## Author

**Aayush Anand**

B.Tech – Computer Science & Engineering

GitHub: [aayush8797823674](https://github.com/aayush8797823674)
