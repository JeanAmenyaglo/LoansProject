Loan Delinquency Risk Analysis
https://img.shields.io/badge/Python-3.7%252B-blue
https://img.shields.io/badge/Jupyter-Notebook-orange
https://img.shields.io/badge/Machine-Learning-purple
https://img.shields.io/badge/License-MIT-green

A comprehensive machine learning project that analyzes loan portfolio data to predict delinquency risk and identify key factors that contribute to loans rolling into later stage delinquency.

📊 Project Overview
This project focuses on building predictive models to assess the risk of loans transitioning from early delinquency to more severe stages. By analyzing historical loan data and delinquency patterns, we develop machine learning classifiers that can help financial institutions proactively manage credit risk.

Business Problem: Predict whether a loan in early delinquency will roll forward into later stage delinquency (60+ days past due).

Solution: Implement and compare multiple classification algorithms to identify the most accurate model for delinquency prediction.

🚀 Quick Start
Prerequisites
Python 3.7+

Jupyter Notebook

Required packages (see requirements.txt)

Installation & Setup
bash
# Clone the repository
git clone <https://github.com/JeanAmenyaglo/LoansProject.git>
cd loans-risk-analytics

# Create virtual environment
python -m venv venv

# Activate environment
# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter Notebook
jupyter notebook
Open loans_risk_analysis.ipynb and run the cells sequentially.

📁 Project Structure
text
loans-risk-analytics/
├── loans_risk_analysis.ipynb      # Main analysis notebook
├── requirements.txt               # Python dependencies
├── README.md                      # Project documentation
└── data/
    └── dataset_risk_analytics.csv # Loan portfolio dataset (5,783 loans)
📈 Dataset Description
The dataset contains 5,783 loans with the following features:

Feature	Description	Type
loan_id	Unique loan identifier	Numerical
monthly_income	Borrower's monthly income	Numerical
origination_score_band	Credit score tier at origination (1-8)	Numerical
TOB_months	Loan age when entering early delinquency	Numerical
closing_principal_balance	Balance at early delinquency	Numerical
original_loan_amount	Original loan amount	Numerical
product	Product line (A, B, C, D)	Categorical
original_loan_term	Original loan term in months	Numerical
remaining_loan_term	Remaining term at early delinquency	Numerical
delq_history	6-month delinquency history (comma-separated)	Text
target	Rolled into later delinquency (1) or not (0)	Binary
Target Variable Distribution:

0 (Not Rolled): ~70% of loans

1 (Rolled): ~30% of loans

🔧 Data Preprocessing
Handling Missing Values
377 missing values identified across multiple columns

Numerical columns: Filled with column means

Categorical columns: delq_history nulls filled with '0,0,0,0,0,0'

Feature Engineering
Label Encoding: Converted product categories to numerical values

Term Grouping: Created binned features for loan terms:

rl_term: Grouped remaining loan term (0-4 bins)

ol_term: Grouped original loan term (0-4 bins)

Final Feature Set for Modeling
text
monthly_income, origination_score_band, TOB_months, 
closing_principal_balance, original_loan_amount, product1, 
rl_term, ol_term
📊 Exploratory Data Analysis
Univariate Analysis
Custom histogram_boxplot() function used to analyze distributions of key variables:

Monthly Income: Right-skewed distribution (750 - 99,750, mean ~14,314)

Origination Score Band: Fairly normal distribution (1-8, mean ~3.9)

Loan Terms: Various distributions analyzed for original and remaining terms

Correlation Analysis
Heatmap analysis revealed relationships between numerical features and the target variable.

🤖 Machine Learning Models
Models Implemented
Logistic Regression - Baseline model

Random Forest Classifier - Ensemble method

Decision Tree Classifier - Interpretable tree-based model

K-Nearest Neighbors - Distance-based classifier

Model Evaluation Metrics
Accuracy Score

Precision, Recall, F1-Score

Confusion Matrix

10-Fold Cross Validation

Feature Importance Analysis

📈 Results & Performance
Model Comparison
Model	Training Accuracy	Cross-Validation Mean	Key Strengths
Random Forest	98.31%	92.37%	Best overall performance
Decision Tree	96.00%	96.52%	High interpretability
K-Nearest Neighbors	76.72%	-	Simple, distance-based
Logistic Regression	69.82%	69.80%	Good baseline
Best Performing Model: Random Forest
Training Accuracy: 98.31%

Cross-Validation Score: 92.37% ± 1.50%

Precision/Recall: 92% for class 1, 91% for class 0

Key Insights from Feature Importance
Random Forest Feature Importance:

closing_principal_balance (Most important)

original_loan_amount

monthly_income

TOB_months

origination_score_band

Decision Tree Feature Importance:

closing_principal_balance

monthly_income

original_loan_amount

origination_score_band

🎯 Business Implications
Risk Factors Identified
High Principal Balance: Loans with higher closing balances show higher delinquency risk

Income Levels: Lower monthly income correlates with increased risk

Loan Age: Time on books (TOB_months) is a significant predictor

Credit Score: Lower origination scores indicate higher risk

Model Applications
Early Warning System: Identify high-risk loans for proactive management

Portfolio Optimization: Adjust risk thresholds based on model predictions

Resource Allocation: Focus collections efforts on highest-risk accounts

🛠️ Technical Implementation
Libraries Used
Data Manipulation: pandas, numpy

Visualization: matplotlib, seaborn

Machine Learning: scikit-learn

Model Evaluation: classification_report, confusion_matrix, cross_val_score

Custom Functions
histogram_boxplot(): Combined visualization for univariate analysis

k_fold(): Cross-validation evaluation wrapper

Model-specific classifier functions with comprehensive evaluation

🚀 Usage Instructions
Data Preparation: Ensure dataset_risk_analytics.csv is in the data folder

Environment Setup: Follow the installation steps above

Execution: Run the Jupyter notebook cells sequentially

Model Training: The notebook will train and evaluate all models automatically

Results Analysis: Review model performance metrics and feature importance plots

🔮 Future Enhancements
Advanced Feature Engineering:

Create delinquency history features from delq_history

Develop ratio features (balance-to-income, etc.)

Model Improvements:

Hyperparameter tuning with GridSearchCV

Ensemble methods (XGBoost, LightGBM)

Neural networks for complex patterns

Deployment:

Create API for real-time predictions

Develop monitoring dashboard

Implement model retraining pipeline

🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

Fork the project

Create your feature branch (git checkout -b feature/AmazingFeature)

Commit your changes (git commit -m 'Add some AmazingFeature')

Push to the branch (git push origin feature/AmazingFeature)

Open a Pull Request

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

📞 Contact
For questions or suggestions regarding this project, please open an issue or contact the maintainers.