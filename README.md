# Capstone Project Overview
This project utilizes the Lending Club dataset to predict loan repayment outcomes, enhancing decision-making and reducing non-performing loans with machine learning techniques.

## Introduction
Peer-to-peer lending connects borrowers with investors, bypassing traditional financial institutions. The Lending Club, a platform in this domain, made public its loan data, allowing for the development of predictive models to forecast loan repayment outcomes.

## Business Problem
The lending industry faces challenges in loan approval times, affecting customer satisfaction and competitiveness. This project aims to create a 'Loan Performance Prediction' system to instantly predict loan request outcomes, streamlining the approval process and reducing default rates.

## Dataset Information
The dataset `lending_club_loan_two.csv` contains information on loans issued through the Lending Club platform, featuring 27 attributes over 396,030 instances from 2007 to 2016. It includes loan amounts, interest rates, borrower employment details, and loan status, among others. The primary objective is to predict the `loan_status` attribute, indicating whether a loan will be fully repaid or charged off. 

### Challenges with Dataset
* Missing values in some features.
* High number of unique values in some categorical features.
* Imbalanced class distribution in the target variable (loan_status).
* Skewed distribution in some features.


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
    |
    ├── Cleanedup, preprocessed and refined CSV data file used for Modeling.
    |

 

### Modeling
Several machine learning models were used to predict loan performance, including Logistic Regression, Decision Trees, XGBoost, CatBoost, and Neural Networks. Decision Trees achieved the highest accuracy (68.00%) and recall (71.40%) scores.

## Conclusion
The project demonstrates the potential of machine learning in transforming the lending industry by enabling faster and more accurate loan approval decisions. The models developed offer valuable insights into factors influencing loan repayment, supporting investors and lenders in risk assessment.

## Next Steps
* Refine the model through advanced hyperparameter tuning.
* Experiment with adjusting the classification thresholds.
* Explore time series and geographic data analysis.
* Develop a credit scoring model.
* Develop a web application for loan performance prediction.



