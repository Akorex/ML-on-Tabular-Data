# Loan-Default-Prediction

This is an ML code training several classifiers like Decision Trees Classifiers and gradient boosting methods like XGBoost to predict what customer would default on the loan given some features. 

We have three csv files for both test and train files. The full dataset can be found [here](https://zindi.africa/competitions/data-science-nigeria-challenge-1-loan-default-prediction/data) 

Notebooks on solution are: Loan default prediction preparation.ipynb and Exploration and modelling.ipynb
Final csv on default prediction is: loandefault_submission.csv
Data Description:
a) Demographic data (traindemographics.csv)

1. customerid (Primary key used to merge to other data)
2. birthdate (date of birth of the customer)
3. bank_account_type (type of primary bank account)
4. longitude_gps
5. latitude_gps
6. bank_name_clients (name of the bank)
7. bank_branch_clients (location of the branch - not compulsory - so missing in a lot of the cases)
8. employment_status_clients (type of employment that customer has)
9. level_of_education_clients (highest level of education)


b) Performance data (trainperf.csv) : This is the repeat loan that the customer has taken for which we need to predict the performance of. Basically, we need to predict whether this loan would default given all previous loans and demographics of a customer.

1. customerid (Primary key used to merge to other data)
2. systemloanid (The id associated with the particular loan. The same customerId can have multiple systemloanid’s for each loan he/she has taken out)
3. loannumber (The number of the loan that you have to predict)
4. approveddate (Date that loan was approved)
5. creationdate (Date that loan application was created)
6. loanamount (Loan value taken)
7. totaldue (Total repayment required to settle the loan - this is the capital loan value disbursed +interest and fees)
8. termdays (Term of loan)
9. referredby (customerId of the customer that referred this person - is missing, then not referred)
10. good_bad_flag (good = settled loan on time; bad = did not settled loan on time) - this is the target variable that we need to predict


c) Previous loans data (trainprevloans.csv) : This dataset contains all previous loans that the customer had prior to the loan above that we want to predict the performance of. Each loan will have a different systemloanid, but the same customerid for each customer.

1. customerid (Primary key used to merge to other data)
2. systemloanid (The id associated with the particular loan. The same customerId can have multiple systemloanid’s for each loan he/she has taken out)
3. loannumber (The number of the loan that you have to predict)
4. approveddate (Date that loan was approved)
5. creationdate (Date that loan application was created)
6. loanamount (Date that loan application was created)
7. totaldue (Total repayment required to settle the loan - this is the capital loan value disbursed +interest and fees) termdays (Term of loan)
8. closeddate (Date that the loan was settled)
9. referredby (customerId of the customer that referred this person - is missing, then not refrerred)
10. firstduedate (Date of first payment due in cases where the term is longer than 30 days. So in the case where the term is 60+ days - then there are multiple monthly payments due - and this dates reflects the date of the first payment)
11. firstrepaiddate (Actual date that he/she paid the first payment as defined above)
