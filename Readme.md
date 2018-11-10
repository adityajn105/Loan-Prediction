# Loan Prediction

Company wants to automate the loan eligibility process (real time) based on customer detail provided while filling online application form. These details are Gender, Marital Status, Education, Number of Dependents, Income, Loan Amount, Credit History and others. To automate this process, they have given a problem to identify the customers segments, those are eligible for loan amount so that they can specifically target these customers. Here they have provided a partial data set.


Variable	|	Description
------------|---------------
Loan_ID	|	Unique Loan ID
Gender	|	Male/ Female
Married|	Applicant married (Y/N)
Dependents|	Number of dependents
Education	|	Applicant Education (Graduate/ Under Graduate)
Self_Employed	|	Self employed (Y/N)
ApplicantIncome	|	Applicant income
CoapplicantIncome	|	Coapplicant income
LoanAmount|	Loan amount in thousands
Loan_Amount_Term	|	Term of loan in months
Credit_History	|	credit history meets guidelines
Property_Area	|	Urban/ Semi Urban/ Rural
Loan_Status	|	Loan approved (Y/N)

## Approach 1
1. Replace Categorical NA values with mode, Non Categorical with mean
2. Replace values above 95,96 percentile of ApplicantIncome, CoapplicantIncome with 95 and 96 percentile respectively.
3. Replace NA Credit History with -1
4. Perform MinMaxScaling on ApplicantIncome, CoApplicantIncome, LoanAmount and Loan Term.
5. Perform LabelEncoding of all other categorical features
6. Try LogisticRegression, SVM, RandomForest, XGBoost. 
7. Perform hypertuning with hyperopt on XGBoost
8. XGBoost is performing with Accuracy = 0.7916666667