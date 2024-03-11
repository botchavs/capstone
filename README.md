# Capstone Project Overview
This project aims to generate a prediction of approval or decline on a loan request from a retail borrower. Multiple machine learning algorithms were used in the project and a dataset from an erstwhile 'peer to peer'(p2p) lender - Lending Club was used to train the ML models. In the project, several ML models used for 'Loan approval' prediction were evaluated to identify the best performing model. This project may be used in a real-life scenario in bank branches as first level of screening for loan requests made by borrowers to branch staff.

## Introduction
P2P lenders connect borrowers with investors, bypassing traditional financial institutions, which have been playing the role of intermediaries. More than a decade ago, a known p2p platform, Lending Club, made its loan data publicly available so that investors could pick assets in which they were interested. The public data has also allowed the development of predictive models to forecast loan repayment outcomes for academic purposes. The dataset is large enough to apply ML models to learn patterns in the dataset.

## Business Problem
When the need for a loan arises, customers usually expect a speedy loan approval, whereas Lenders process requests based on available resources and process constraints. Any bottlenecks or delays in loan processing affect customer satisfaction and competitiveness. This project aims to create a 'Loan Performance Prediction' system to instantly predict loan request outcomes, streamlining the approval process and reducing default rates.

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
    ├── Cleanfile.csv                       <- Cleanedup, preprocessed and refined CSV data file used for Modeling.
    |
    ├── Demo App
    |   ├── best_model.pkl                  <- Best model saved for using in the demo app
    |   ├── Loan_predict_app.py             <- python code file for Streamlit app
    |


### Modeling
Multiple ML models used for prediction - Logistic Regression, Decision Trees, XGBoost, CatBoost, and Neural Networks. We evaluated the models and plotted accuracy and recall scores. We established that recall scores is more appropriate than accuracy to consider for loan performance prediction, as it is crucial not to misclassify the likely default loans as fully paid loans. Neural networks achieved the highest test recall score with 66.80%, but we have considered Logistic regression with recall score of 66.20% as the best model.

## Conclusion
The project demonstrates the potential of machine learning to transform the lending industry by enabling faster loan approval decisions. According to ML models, the accuracy of loan approval prediction ranges between 65% and 70%. In the real world, stakeholders expect a much higher accuracy when deploying the model. However, with a large dataset and better data collection, it is possible to achieve a higher accuracy or recall score.

## Next Steps
* ROC/AOC for multiple algorithms other than logistic regression.
* Explore time series analysis.
* Develop a credit scoring model.



