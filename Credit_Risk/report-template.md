# Module 12 Report Template

## Overview of the Analysis
Lending companies, such as banks, provide loans to clients with the expectation of repayment with interest. Before approving loans, these companies assess various factors to evaluate the risk of lending. Key indicators include credit history, credit score, and other financial metrics. In this challenge, these indicators were provided in the lending_data_csv file, including:

Loan Size
Interest Rate
Borrower Income
Debt-to-Income Ratio
Number of Accounts
Derogatory Marks
Total Debt

These variables are the independent features, and Loan Status is the target variable. Loan Status is binary: 0 for a healthy loan and 1 for a high-risk loan. We used Logistic Regression for this classification task, as it is effective for predicting binary outcomes.

Stages of the Machine Learning Process

1. **Exploration and Preparation:**
We began by exploring the data to understand its structure and the relationships between features. The data was divided into features (X) and the target variable (y). We used train_test_split from sklearn to split the data into training (75%) and testing (25%) sets.

2. **Model Implementation:**
We implemented a Logistic Regression model with a random state of 1 to ensure reproducibility. The model was trained on the training set and tested on the testing set.

 3. **Model Evaluation:**
We used a confusion matrix to evaluate the model's performance, which provided insights into true negatives, true positives, false negatives, and false positives. The confusion matrix results were:

<img width="570" alt="Screenshot 2024-08-25 at 10 00 45 PM" src="https://github.com/user-attachments/assets/cf5f9534-ecad-49ac-86b6-f5db64628c3f">

## Results
The classification report for our model shows:

<img width="459" alt="Screenshot 2024-08-25 at 9 57 19 PM" src="https://github.com/user-attachments/assets/74b5e173-0ae6-46db-8e56-660a2ab63a69">

**Accuracy:** The model's accuracy is 99%. This high accuracy is partly due to the dataset imbalance, with more healthy loans than high-risk loans, which can skew this metric.

**Precision:** The model achieved 100% precision for healthy loans and 85% for high-risk loans.

**Recall:** The recall is 99% for healthy loans and 91% for high-risk loans, indicating the model's effectiveness in identifying most of the true positives for both classes.

## Summary
The model performs very well, especially in predicting healthy loans. However, due to the imbalance in the dataset, it’s crucial to address this issue for more accurate predictions of high-risk loans. The model had 102 false positives and 56 false negatives, which can affect decision-making. For example, false positives might lead to approving loans that are actually high-risk, while false negatives might result in denying healthy loans.

- Recommendations:

**Balanced Dataset:** To improve the model, consider using a more balanced dataset or applying techniques to handle class imbalance, such as oversampling the minority class or using synthetic data generation.

**Alternative Metrics:**  Use additional evaluation metrics like ROC-AUC to better understand model performance on imbalanced data.
Overall, improving how the model handles class imbalance will enhance its reliability in predicting both healthy and high-risk loans.

