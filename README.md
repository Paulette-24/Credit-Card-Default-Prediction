# Credit Default Prediction and Financial Risk Analysis
![image](credit-risk-analysis.jpg)

## Links
[Kaggle Dataset – Give Me Some Credit](https://www.kaggle.com/c/GiveMeSomeCredit)

## Project Overview
In this project, I developed a predictive model to identify individuals who are likely to default on loans or experience financial distress within the next two years. By analyzing behavioral patterns such as payment history, debt levels, and credit usage the model helps financial institutions reduce risk, improve loan portfolio quality, and proactively manage high-risk customers.

## Business Understanding
### Stakeholder Audience
This project is targeted toward:
- **Credit Risk Teams** to strengthen existing scoring models
- **Loan Approval Departments** to screen applicants more effectively
- **Executives and Analysts** for strategic insight into borrower behavior and risk mitigation

### Dataset Choice
The dataset was sourced from [Kaggle](https://www.kaggle.com/c/GiveMeSomeCredit) and includes 150,000 records of individual credit profiles with key financial indicators and a target variable indicating financial distress within two years.

## Data Understanding
The dataset includes the following key features:

**RevolvingUtilizationOfUnsecuredLines** – Percentage of available credit used

**age** – Age of the borrower in years

**DebtRatio** – Monthly debt payments divided by gross monthly income

**MonthlyIncome** – Self-reported income

**NumberOfOpenCreditLinesAndLoans** – Number of active credit lines

**NumberOfTimes90DaysLate** – Count of times the borrower was over 90 days late

**NumberRealEstateLoansOrLines** – Count of real estate credit accounts

**NumberOfTime60-89DaysPastDueNotWorse** – Times late 60–89 days

**NumberOfDependents** – Number of dependents claimed

**SeriousDlqin2yrs** – Target: 1 = financial distress, 0 = no distress

## Data Preparation
### The data was cleaned and prepared by:
1. Handling missing values
2. Removing duplicate records
3. Identifying and handling outliers using boxplots and z-scores
4. Scaling numerical features using `StandardScaler`
5. Engineering new features such as:
   - `Has_90_DPD` (This is a binary flag (0 or 1) that indicates whether a person has ever been 90 or more days late on a credit payment.)
   - `IncomeToDebtRatio`
   - `UtilizationPerAccount`
   - `DebtBurden`
   - `TotalDelinquencies`

## Data Analysis
### The analysis addressed questions like:
1. What features are most associated with defaults?
2. How can feature engineering improve prediction?
3. What is the impact of late payment behavior on default risk?
4. Which model best balances accuracy and risk flagging?

## Results
### Key Findings
1. Individuals with 90+ day payment delays were far more likely to default.
2. Lower income-to-debt ratios correlated with higher risk.
3. Custom features like `DebtBurden` and `Has_90_DPD` added strong predictive value.
4. The Gradient Boosting model showed the best performance with an **AUC of 0.87**.

## Visualizations
### Correlation Heatmap  
To identify relationships between features and detect multicollinearity.

### Boxplots & Countplots  
To visualize patterns in financial behavior by distress outcome.

### ROC Curve  
To evaluate model performance and its trade-off between true and false positives.

### Feature Importance  
Tree-based models highlighted the impact of custom features like delinquency flags.

## Modeling
I trained and tested several models including:
- Logistic Regression
- Random Forest Classifier
- Gradient Boosting Classifier (final)

The final model (Gradient Boosting) was selected based on its balance of:
- Accuracy: 87%
- Precision: 82%
- Recall: 69%
- AUC-ROC: 0.87

## Feature Engineering
Custom features based on financial logic:
- Binary flags for past due history
- Normalized credit utilization
- Debt burden approximation
- Summed delinquencies

##Evaluation

The final model’s metrics:
- **Accuracy**: 87%
- **Precision**: 82%
- **Recall**: 69%
- **F1 Score**: 75%
- **AUC-ROC**: 0.87

These results show a strong ability to flag high-risk individuals while keeping false positives manageable.

## Conclusion
- Borrowers with past 90+ day delinquencies are significantly more likely to default.
- High debt and low income-to-debt ratios raise risk flags.
- Feature engineering played a key role in model performance.
- The Gradient Boosting model was the most effective, with reliable predictive power across evaluation metrics.

## Next Steps
- Deploy this model in a real-time credit scoring pipeline.
- Monitor at-risk customers and intervene early with support or adjusted terms.
- Explore further behavioral and external data to improve accuracy.
- Use SHAP or LIME for interpretability in production.
