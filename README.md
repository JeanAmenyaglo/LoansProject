Loans Project - Risk Analytics
https://img.shields.io/badge/Python-3.7%252B-blue
https://img.shields.io/badge/Jupyter-Notebook-orange
https://img.shields.io/badge/License-MIT-green

A comprehensive risk analytics project analyzing loan portfolio data to predict delinquency behavior using Python and Jupyter Notebook.

📋 Project Overview
This project performs exploratory data analysis and predictive modeling on a loan portfolio dataset to assess risk factors associated with early delinquency and loan roll-forward into later stage delinquency.

Key Objectives:

Identify patterns and risk factors in loan delinquency

Prepare data for predictive modeling

Build foundation for risk assessment models

🚀 Quick Start
Get started in under a minute:

bash
# Clone the repo
git clone <https://github.com/JeanAmenyaglo/LoansProject.git>
cd <repo-folder>

# Create and activate virtual environment
python -m venv ./venv

# Windows
.\venv\Scripts\activate
# macOS/Linux
source ./venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter Notebook
jupyter notebook
Then, open loans_risk_analysis.ipynb in the Jupyter interface and run the cells sequentially.

📊 Workflow
text
Raw Loan Data (CSV)
        │
        ▼
 Data Loading & Cleaning
        │
        ▼
Exploratory Data Analysis (EDA)
- Univariate analysis
- Data quality checks  
- Visualizations
        │
        ▼
Feature Engineering
- Transform delq_history
- Create derived metrics
        │
        ▼
Predictive Modeling
- Logistic Regression / Classification
- Model training & evaluation
        │
        ▼
Model Insights & Risk Assessment
📁 Project Structure
text
loans-risk-analytics/
├── loans_risk_analysis.ipynb  # Main analysis notebook
├── requirements.txt           # Python dependencies
├── README.md                  # Project documentation
└── data/
    └── dataset_risk_analytics.csv  # Loan portfolio dataset
🛠️ Setup Instructions
1. Create Virtual Environment
bash
python -m venv ./venv

# Activate environment
# Windows
.\venv\Scripts\activate
# macOS/Linux
source ./venv/bin/activate
2. Install Dependencies
bash
pip install -r requirements.txt
3. Save Dependencies
bash
pip freeze > requirements.txt
📈 Dataset Description
The dataset contains 5,783 loans with the following features:

Feature	Description
loan_id	Unique loan identifier
monthly_income	Borrower's monthly income
origination_score_band	Score tier band at origination (1-8)
TOB_months	Age in months when loan entered early delinquency
closing_principal_balance	Closing balance at early delinquency
original_loan_amount	Original loan amount
product	Product line (A, B, C, D)
original_loan_term	Original loan term in months
remaining_loan_term	Remaining term in months at early delinquency
delq_history	Previous 6 months delinquency history (comma-separated)
target	Whether loan rolled into later stage delinquency (1: rolled, 0: not rolled)
🔍 Analysis Steps
Data Loading & Initial Exploration
Import libraries: pandas, numpy, matplotlib, seaborn, scikit-learn

Load dataset and inspect basic information

Data quality assessment

Data Preprocessing
Fill numeric nulls with column means

Fill categorical nulls in delq_history with '0,0,0,0,0,0'

Verify no remaining null values

Exploratory Data Analysis (EDA)
Univariate analysis using custom histogram_boxplot() function

Distribution analysis of key variables

Data quality checks and missing patterns

📊 Key Findings
Total Records: 5,783 loans with 11 features

Missing Values: 377 nulls successfully addressed

Monthly Income: Range 750–99,750, mean ~14,314

Origination Score Band: 1–8, mean ~3.9

Target Variable: ~30% of loans rolled into later delinquency

🛠️ Technical Implementation
Libraries Used
pandas, numpy - Data manipulation

matplotlib, seaborn - Data visualization

scikit-learn - Machine learning

Custom Functions
histogram_boxplot(): Combines boxplots and histograms for univariate analysis

Includes mean/median lines and configurable bins

🎯 Next Steps
Feature engineering from delq_history

Multivariate analysis and correlation studies

Predictive modeling using logistic regression or other classifiers

Model evaluation and validation

📝 Usage
Ensure all required libraries are installed

Place dataset_risk_analytics.csv in the working directory

Execute notebook cells sequentially in loans_risk_analysis.ipynb

🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

