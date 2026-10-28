# Online Gaming Addiction Prediction in Bangladesh

## Project Overview

This is our CSE437 research project at BRAC University, where we compared different Machine Learning (ML) and Deep Learning (DL) models to predict online gaming addiction in Bangladesh.

Our main goal was to find out how well these models perform on the same dataset and whether using detailed gaming behavior features gives better results than using only basic information such as age, gender, gaming frequency, and opinion.

## Dataset

We used a publicly available survey dataset from Kaggle with **293 responses** and **12 columns**, including the target variable `Class`.

- **170** respondents were labeled non-addicted (`N`).
- **123** respondents were labeled addicted (`Y`).

We tested two feature settings:

- **Setting A:** All 11 available features, including gaming behavior criteria such as Salience, Tolerance, Mood Modification, Withdrawal, Relapse, Conflict, and Problems.
- **Setting B:** Only Age, Gender, Frequency, and Opinion.

## What We Did

We cleaned the dataset, handled missing values, encoded categorical features, and scaled numerical features. We used preprocessing pipelines to reduce data leakage during model training and evaluation.

For a fair comparison, we used an **80/20 stratified train-test split** and **5-fold stratified cross-validation** on the training data. We evaluated the models using Accuracy, Precision, Recall, F1-score, ROC-AUC, and PR-AUC.

We compared these models:

**Machine Learning:** Logistic Regression, SVM, KNN, Gaussian Naive Bayes, Decision Tree, Random Forest, Extra Trees, Gradient Boosting, AdaBoost, and XGBoost.

**Deep Learning:** PyTorch MLP, MLP with Batch Normalization, and Residual MLP.

We also performed K-Means clustering and PCA visualization for additional analysis.

## Results

The models performed much better when all features were included.

| Setting | Best Model | Accuracy | F1-score | ROC-AUC |
| --- | --- | --- | --- | --- |
| A (All Features) | PyTorch MLP | 94.9% | 0.941 | 0.989 |
| B (Basic Features) | AdaBoost | 78.0% | 0.723 | 0.794 |

In Setting A, XGBoost also performed well, with **94.9% accuracy** and an **F1-score of 0.939**.

Our results showed that detailed gaming behavior features were more useful for predicting the survey's addiction labels than basic demographic and gaming usage information alone. We also found that a relatively simple deep learning model could perform competitively with traditional ML models.

Since the dataset is small, these results should be treated as research findings rather than a reliable clinical diagnosis tool.

## Technologies Used

Python, Pandas, NumPy, Scikit-learn, PyTorch, XGBoost, Matplotlib, and Google Colab.

## Team Members and Contributions

This project was completed by four members from the Department of Computer Science and Engineering, BRAC University.

- **Abdul Gaffar Imon:** Data cleaning, label standardization, and unsupervised analysis.
- **Shaon Mohammod Hassan:** Feature engineering, experimental feature settings, preprocessing pipelines, and data-splitting utilities.
- **Montasir Mogumder Shariar:** Machine learning model training, cross-validation, evaluation, and diagnostic plots.
- **Saib Saleh Nabil:** Deep learning models, training, evaluation, and final model comparison.

## Running the Project

1. Open the Python script in Google Colab or a Python environment.
2. Install the required libraries: `numpy`, `pandas`, `scikit-learn`, `torch`, `matplotlib`, `openpyxl`, and `xgboost` (optional).
3. Make sure the dataset is accessible through the Google Sheets export URL used in the script, or update the data-loading section to use your own copy.
4. Run the code in order. Results tables are exported as CSV files to the `results/` folder.

## Future Work

In the future, this work can be improved by using a larger and more diverse dataset, testing model performance on external data, and analyzing which features influence predictions the most.
