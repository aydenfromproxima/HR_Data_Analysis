**HR Data Analytics – Salary Prediction & Workforce Insights**

**Dataset Overview**

The dataset contains 5000 employee records with 20 features, including:

Gender
Business
Dependancies
Calls
Type (Contract Type)
Billing
Rating
Age
Salary
Base Pay
Bonus
Unit Price
Volume
Opening Balance
Closing Balance
Low
Unit Sales
Total Sales
Months (Tenure)
Education

**Key details:**

Missing values were present in Base Pay, Opening Balance, and Total Sales and handled via KNN Imputer 
Final dataset after cleaning had zero missing values.

**Data Preparation**

In the notebook, I:

 Loaded CSV and inspected data shape → 5000 rows × 20 columns
 Identified missing values
 Replaced missing values using KNN Imputer
 Converted categorical columns using Label Encoding
 Checked distributions using boxplots
 Removed outliers using IQR method (validated via re-plotted boxplots) 
 Performed feature selection using Spearman correlation

**Analysis & Visualizations**

The project includes several visualizations and analytical steps:

1. Gender Distribution

Employee count is nearly equal:

2528 Male
2472 Female 

2. Education Breakdown

PG → 2979
Graduation → 1980
Intermediate → 27
High School → 14

3. Contract Type Distribution

Month-to-Month → 2777
Two Year → 1195
One Year → 1028

4. Salary Distribution & Outliers

Visualized Salary, Base Pay, Bonus, etc. via boxplots.
Found significant outliers and removed them.

5. Salary Correlations

Spearman correlation showed extremely strong relationships:

Total Sales → Salary (0.99) (perfect monotonic relation)

Bonus, Base Pay, Unit Sales also highly correlated (>0.8)
Thus, these became key predictors.

6. Numerical Feature Relationships

Scatter plots showed:
Higher Total Sales → Higher salary
Higher Bonus → Higher salary
More Months (experience) → Higher salary

7. Categorical Impact on Salary

Education strongly impacts salary.
PG employees earn ₹50,000 – ₹2,00,000
High School / Intermediate employees earn < ₹25,000
Gender has nearly no salary difference.

8. Company Hiring Trends

Last four months saw 765 hires, while 269 employees have long tenure (72 months).

**Machine Learning Models after cleaning, encoding, scaling, and feature selection:**

Linear Regression → 78.27%
Decision Tree Regression → 99.35%
Random Forest Regression → 99.09%
XGBoost Regression → 99.24% (best performance) 
Cross Validation Results
Random Forest CV Accuracy → 0.99993
XGBoost CV Accuracy → 0.99961

**Final Model**

 XGBoost Regressor
 StandardScaler for normalization
 Model exported as hr.pkl
 Scaler exported as schr.pkl
 Deployed using both Tkinter and Streamlit interfaces

**Key Insights**

Salary is most influenced by:
Age
Education
Months of experience
Total Sales & Performance metrics
Higher sales directly increase salary.
Education level strongly impacts salary brackets.
The company prefers hiring highly educated & experienced employees.
Gender plays no significant role in salary differences.
Strong correlations allowed the ML model to achieve very high accuracy.

**Languages & Libraries Used**

Python
Pandas
NumPy
Scikit-learn
XGBoost
Seaborn
Matplotlib
Pingouin
Tkinter
Streamlit

**How to Run the Project**
1. Clone the repository
git clone https://github.com/yourusername/HRDataAnalytics.git

2. Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn xgboost streamlit

3. Run the notebook
jupyter notebook HRDataAnalytics.ipynb

4. Run Streamlit App
streamlit run hrapp.py

**Future Improvements**

Add SHAP analysis for model explainability
Implement HR attrition predictions
Build PowerBI or Streamlit dashboards
Add feature importance visualizations
Deploy as a web-based prediction tool

Contributing

Pull requests are welcome!
Feel free to add new visualizations, models, or improvements.

If You Found This Useful

Star this repository to support more data analytics projects!
