# Capstone Project Overview

## Introduction
This document provides an initial overview of the capstone project, highlighting the project domain, targeted problems, and the dataset proposed for analysis and modeling.

### Area of Interest
For the Capstone project, the chosen domain is Banking. The dataset used is from LendingClub.com, a peer-to-peer lender in the United States until 2020.

### Dataset Information
Multiple datasets from Lending Club were used, spanning years from 2007 to 2020. The dataset of interest is [lending_club_loan_two.csv](https://www.kaggle.com/datasets/jeandedieunyandwi/lending-club-dataset/code?datasetId=608703&sortBy=voteCount), with a manageable size for analysis.

### Dataset Overview
- Rows: 396,030
- Columns: 27
- Period: 2007 to 2016

### Challenges with Larger Datasets
Working with datasets larger than 1 GB presented challenges in downloading and loading into Jupyter Notebook and Google Colab. Larger datasets led to mixed datatype warnings, and exploring the dataset using `df.info()` and `df.describe()` took a long time, causing system crashes.

### Selected Datasets
The selected smaller-sized datasets, highlighted in green, have a reduced number of columns (27) and rows ranging from 300k to 400k. For the current analysis, [lending_club_loan_two.csv](https://www.kaggle.com/datasets/jeandedieunyandwi/lending-club-dataset/code?datasetId=608703&sortBy=voteCount) is chosen.

## Dataset Details
The dataset contains loans extended by Lending Club to its customers.

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



### Modeling
Through modeling of dataset, we shall predict the "loan_status," which may take two values either "Fully Paid" or "Charged Off" indicating a loss.

### Cleaning & Exploratory Data Analysis
The dataset appears to be relatively clean, with a few missing values. Further analysis is required to clean the dataset.

### Link to the Dataset
[Dataset Link](https://www.kaggle.com/datasets/jeandedieunyandwi/lending-club-dataset/code?datasetId=608703&sortBy=voteCount)