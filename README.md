# Loans Project - Risk Analytics

## Overview
This Jupyter Notebook analyzes a loan portfolio dataset to assess risk factors associated with early delinquency and loan roll-forward into later stage delinquency. The project performs exploratory data analysis (EDA) and prepares the data for predictive modeling.

## Dataset Description
The dataset contains information about 5,783 loans with the following features:

- **loan_id**: Unique loan identifier
- **monthly_income**: Borrower's monthly income
- **origination_score_band**: Score tier band at loan origination (1-8)
- **TOB_months**: Age in months when loan entered early delinquency
- **closing_principal_balance**: Loan's closing balance at early delinquency
- **original_loan_amount**: Original loan amount
- **product**: Product line (A, B, C, D)
- **original_loan_term**: Original loan term in months
- **remaining_loan_term**: Remaining term in months at early delinquency
- **delq_history**: Previous 6 months of delinquency history (comma-separated values)
- **target**: Whether loan rolled forward into later stage delinquency (1: rolled, 0: not rolled)

## Project Structure

### 1. Data Loading and Initial Exploration
- Import necessary libraries (pandas, seaborn, numpy, scikit-learn, matplotlib)
- Load the dataset from 'dataset_risk_analytics.csv'
- Display basic dataset information and statistics

### 2. Data Preprocessing
- Handle missing values by:
  - Filling numeric nulls with column means
  - Filling categorical nulls in 'delq_history' with '0,0,0,0,0,0'
- Verify no remaining null values

### 3. Exploratory Data Analysis (EDA)
- **Univariate Analysis**: 
  - Custom function `histogram_boxplot()` to visualize numerical variables
  - Distribution analysis of key variables like monthly_income and origination_score_band
- **Data Quality Checks**:
  - Check for unique values in each column
  - Identify data types and missing value patterns

## Key Findings from Initial EDA

### Data Quality
- 5,783 total records with 11 features
- 377 missing values across multiple columns (successfully handled)
- Mixed data types: numerical (float64, int64) and categorical (object)

### Variable Insights
- **monthly_income**: Wide range from 750 to 99,750 with mean ~14,314
- **origination_score_band**: Scores range from 1-8, mean ~3.9
- **target**: Approximately 30% of loans rolled into later delinquency

## Technical Implementation

### Libraries Used
- **pandas**: Data manipulation and analysis
- **seaborn & matplotlib**: Data visualization
- **numpy**: Numerical computations
- **scikit-learn**: Machine learning utilities

### Custom Functions
- `histogram_boxplot()`: Combines boxplots and histograms for comprehensive univariate analysis
- Handles different bin sizes and shows mean/median lines

## Next Steps
The notebook is prepared for further analysis including:
- Feature engineering from delq_history
- Multivariate analysis and correlation studies
- Predictive modeling using logistic regression or other classification algorithms
- Model evaluation and validation

## Usage
To run this analysis:
1. Ensure all required libraries are installed
2. Place 'dataset_risk_analytics.csv' in the working directory
3. Execute cells sequentially

This project provides a foundation for building risk assessment models to predict loan delinquency behavior in financial portfolios.
