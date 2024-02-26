# Capstone Project Overview

## Introduction
Peer-to-peer (P2P) lending has revolutionized the way people borrow and invest money. In the aftermath of the 2008 financial crisis, platforms like Lending Club gained prominence by facilitating loans without traditional financial institutions as intermediaries. At its peak, Lending Club was the world's largest P2P lender, boasting assets of approximately $16 billion by 2015-2016. What is P2P Lending? "Peer-to-peer lending (P2P) is an innovative form of borrowing and investing money without the involvement of traditional financial institutions. Using online platforms, borrowers and lenders can make mutually beneficial transactions directly without the need a bank as an intermediary.

"Peer-to-peer (P2P) lending works by connecting borrowers who need money with lenders who want to make a return on their investments. Borrowers submit loan requests to the peer-to-peer lender, and investors compete to finance the loans in exchange for an interest rate. From start to finish, P2P sites manage the entire process, including rating creditworthiness, loan servicing, payments, and collections" - p2pmarketdata.

The Lending Club platform had offered personal and small business loans ranging from 500 USD to 40000 USD. To attract more investors, Lending Club had made its loan dataset public so that investors can make an informed choice on whether to invest in a a specific loan asset.

This project leverages the Lending Club dataset to build a predictive model that determines the likelihood of loan repayment. This analysis is a part of the Capstone project under the Data Science Diploma Program at BrainStation, Vancouver.

## Business Problem
In Banking and financial Lending, one of the issues of frustration for borrowers is the time taken by Lending institutions to approve a loan request. This process can span several days to weeks before the borrower receives confirmation of approval or denial. During this uncertain waiting period, and in pursuit of more favorable loan terms, borrowers often apply for the same loan with multiple lenders.

Consequently, it is in the lender's best interest to quickly process and communicate the loan offer details. Speedy approvals not only improve customer experience but also mitigate the risk of potential borrowers opting for competing lenders.

The goal is to develop a 'Loan Performance Prediction' system that can instantly predict the outcome of loan requests using preliminary data. This system is aimed to assist consumer and small business loans as well as commercial loans, improving the decision-making process and potentially reducing non-performing loans. This application can be powered by a machine learning model trained on a large dataset of historical loan performance data. With this foundation, let's dive into the analysis and model building process.

=============================================================
## Project Organization
=============================================================

    ├── README.md                           <- Main README document for developers.
    |
    ├── lending_club_loan_two.csv           <- Dataset (source: [Kaggle](https://www.kaggle.com/datasets/jeandedieunyandwi/lending-club-dataset/code?datasetId=608703&sortBy=voteCount)) 
    |
    ├── Presentation_final.pdf              <- Final project presentation.
    |
    ├── notebooks
    |   ├── Capstone_Sprint 1.ipynb         <- Project notebook 1 - data preparation and exploration.
    |   ├── Capstone_Sprint 2.ipynb         <- Project notebook 2 - baseline modeling.
    |   └── Capstone_working.ipynb          <- Project notebook 3 - final models for Loan performance prediction.


=============================================================

### Dataset Information
The dataset of interest is [lending_club_loan_two.csv](https://www.kaggle.com/datasets/jeandedieunyandwi/lending-club-dataset/code?datasetId=608703&sortBy=voteCount), with a manageable size for analysis.

### Dataset Overview
- Rows: 396,030
- Columns: 27
- Period: 2007 to 2016

### Challenges with Dataset
Addressing data quality issues was a key part of preparing our dataset for analysis:

- Null Values: Notable missing data was found in features like mort_acc (9.54%), emp_length (4.62%), and others, requiring targeted imputation strategies. 
- Categorical Complexity: High category count in some features necessitated dimensionality reduction and encoding.
- Imbalanced Data: An 80:20 split in the target variable called for rebalancing to avoid prediction bias. We used SMOTE to deal with imbalance.
- Skewed Distribution: Non-normal distributions in certain variables were corrected through log transformation.

These steps were critical to ensure the dataset's readiness for robust predictive modeling..

## Dataset Details
This Jupyter notebook is part of my Capstone project under the Data Science Diploma Program at BrainStation, Vancouver. In this notebook, we use popular python Python libraries to analyze a dataset of Lending Club. The loans dataset contains 27 features of more than 300,000 loans availed by borrowers through Lending Club spanning from 2007 to 2018. Types of features captured in the dataset are loan-specific features, borrower-specific personal and financial details. The key feature in the dataset is loan_status, which is our target variable and has two values 'Fully Paid' or 'Charged Off'. 'Fully Paid' implies loan was fully repaid. 'Charged Off' implies there was default or short payment by borrower and corresponding investors had to write off atleast part of the loan. All these loans featured in the dataset were closed loans and no running loans were captured in this dataset.

### Data Dictionary
There are 27 columns names in the data dictionary
| S.No | Column Name           | Description                                                                                                 |
|------|-----------------------|-------------------------------------------------------------------------------------------------------------|
| 0    | loan_amount           | The listed amount of the loan applied for by the borrower. If at some point in time, the credit department reduces the loan amount, then it will be reflected in this value.|
| 1    | term                  | The number of payments on the loan. Values are in months and can be either 36 or 60.                          |
| 2    | int_rate              | Interest Rate on the loan                                                                                    |
| 3    | installment           | The monthly payment owed by the borrower if the loan originates.                                            |
| 4    | grade                 | LC assigned loan grade                                                                                      |
| 5    | sub_grade             | LC assigned loan subgrade                                                                                   |
| 6    | emp_title             | The job title supplied by the Borrower when applying for the loan.*                                           |
| 7    | emp_length            | Employment length in years. Possible values are between 0 and 10 where 0 means less than one year and 10 means ten or more years.|
| 8    | home_ownership        | The homeownership status provided by the borrower during registration or obtained from the credit report. Our values are: RENT, OWN, MORTGAGE, OTHER|
| 9    | annual_inc            | The self-reported annual income provided by the borrower during registration.                                 |
| 10   | verification_status   | Indicates if income was verified by LC, not verified, or if the income source was verified                    |
| 11   | issue_d               | The month which the loan was funded                                                                         |
| 12   | loan_status           | Current status of the loan                                                                                 |
| 13   | purpose               | A category provided by the borrower for the loan request.                                                   |
| 14   | title                 | The loan title provided by the borrower                                                                    |
| 15   | zip_code              | The first 3 numbers of the zip code provided by the borrower in the loan application.                         |
| 16   | addr_state            | The state provided by the borrower in the loan application                                                  |
| 17   | dti                   | A ratio calculated using the borrower’s total monthly debt payments on the total debt obligations, excluding mortgage and the requested LC loan, divided by the borrower’s self-reported monthly income.|
| 18   | earliest_cr_line      | The month the borrower's earliest reported credit line was opened                                            |
| 19   | open_acc              | The number of open credit lines in the borrower's credit file.                                               |
| 20   | pub_rec               | Number of derogatory public records                                                                        |
| 21   | revol_bal             | Total credit revolving balance                                                                             |
| 22   | revol_util            | Revolving line utilization rate, or the amount of credit the borrower is using relative to all available revolving credit.|
| 23   | total_acc             | The total number of credit lines currently in the borrower's credit file                                     |
| 24   | initial_list_status   | The initial listing status of the loan. Possible values are – W, F                                           |
| 25   | application_type      | Indicates whether the loan is an individual application or a joint application with two co-borrowers         |
| 26   | mort_acc              | Number of mortgage accounts.                                                                               |
| 27   | pub_rec_bankruptcies  | Number of public record bankruptcies 




### Cleaning 
Unique Value Challenges
High Cardinality Columns: Certain columns exhibit a large percentage of unique values, which complicates analysis and encoding efforts:
- address: 99% unique, may be dropped post-extraction of relevant information like city, state, and pin code.
- emp_title: 46% unique, potentially droppable as it offers limited analytical value.
Duplicate Records: No duplicate rows were detected in the dataset, indicating a unique dataset without redundancies.
Null Value Analysis: Missing Data: Several columns have a notable percentage of missing values:
Column `mort_acc` has 9.5% nulls was imputed with mean values and `emp_length` has 4.6% nulls, has been dealt with by removing column.
`title`, `pub_rec`, `revol_util`with than 0.5% nulls have been addressed by removing corresponding rows or columns.

### Feature Engineering
Extract "State" from column `address` and extracted `Month` and `Year` from column `issue_d`. We have retained all the numerical columns since they mostly exhibited a normal distribution.


### Exploratory Data Analysis
Since certain columns exhibited a significant right skew in their distributions, log transformation has been applied to these features, resulting in a more normalized distribution. Most of the bivariate plots showed a non-linear relationship or no relationship and linear models may not be suitable for modeling these relationships. loan_amount,open_acc, annual_inc,pub_rec,recol_bal,revol_util,mort_acc,month,year had little effect on loan_status variable and were not a strong differentiator in predicting loan status. 75% of loans have 3 years tenor and remaining have 5 year tenor.Grades B and C have the highest loans, followed by A and D.
Most of the loans have have home ownership listed as mortgage, followed by rent. 80% of loans are under 'Fully paid' category and remaining 20% are under 'Charged Off' category. Too many categories in purpose. Most of the applications have individual category. Maximum loans are in the range of 5k to 12.5k USD. Minimum loans are extended in range of 27k to 32k USD. Most loans are in the range of 11% to 16%. The loans above 21% taper off.

### Modeling
Through modeling of dataset, we shall predict the "loan_status," which may take two values either "Fully Paid" or "Charged Off" indicating a loss. We used train test split and used standard scaler for standardisation and normalisation. Since this is a binary classification problem, we used Logistics regression, XGBoost, CatBoost, 


**Model Performance Summary for Accuracy:**
Among the models considered for loan default prediction, Decision Trees demonstrate the highest accuracy at 68.00%, closely followed by Logistic Regression and Neural Networks, both achieving almost equal accuracy levels.

| Model                     | Optimum Test Accuracy Score |
|---------------------------|---------------------|
| Logistic Regression       | 67.10%              |
| Decision Trees            | 68.00%              |
| XGBoost                   | 66.90%              |
| CatBoost                  | 63.00%              |
| Neural Networks           | 67.70%              |


**Model Performance Summary for Recall score:**

Considering recall scores for loan prediction, as opposed to solely focusing on accuracy, is crucial for several reasons: 

* Accuracy measures the proportion of true results (both true positives and true negatives) among the total number of cases examined. It's a general measure of how often the model is correct.
* Recall measures the proportion of actual positives (e.g., defaulters) that are correctly identified. It specifically focuses on the model's ability to detect defaulted cases.

Importance of Recall in Loan Prediction: Mitigating Financial Risks: In loan prediction, missing a potential defaulter (a false negative) can be costlier than wrongly identifying a non-defaulter as a defaulter (a false positive). Regulatory Compliance: Financial institutions often face regulatory requirements to manage and minimize credit risks effectively. High recall ensures that risky loans are identified more accurately. Balancing Profit and Risk: While accuracy provides an overall effectiveness of the model, recall specifically helps in balancing the portfolio's risk by accurately identifying higher-risk loans.


Comparison of Recall scores for different models

| Model                     | Optimum Test Recall Score | Hyperparameter   |
|---------------------------|-------------------|------------------|
| Logistic Regression       | 66.20%            | C = 0.1          |
| Decision Trees            | 71.40%            | Max depth = 2    |
| XGBoost                   | 60.50%            | Estimators = 3   |
| CatBoost                  | 63.00%            | Estimators = 7   |
| Neural Networks           | 67.70%            | Epochs = 5       |

The best model is Decision Trees with 71.4%, which is a decent predictive performance to be used by Lenders to predict loan performance. It may be noted that best scores were 


### Next Steps
Next Steps
* The next steps involve refining the model through advanced hyperparameter tuning.This project only scratched the surface of hyperparameter optimization.
* We can experiment with adjusting the classification thresholds.
* A challenge encountered was the excessive complexity of the models in relation to my dataset, necessitating the simplification of models by adjusting various hyperparameters.
* Further analysis could include examining time series and geographic data.
* There's also scope for enhanced feature engineering.
* Additionally, developing a credit scoring model is another avenue to explore.
* Developing a web app for demonstrating prediction of loan performance over the tenor.

