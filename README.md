# HR Data Analytics – Salary Prediction & Workforce Insights

A comprehensive data analytics and machine learning project exploring 5,000 employee records to understand salary drivers, workforce patterns, and predictive modeling for HR decision-making.

---

## Dataset Overview

The dataset contains **5000 employee records** with **20 features**, including:

- Gender  
- Business  
- Dependancies  
- Calls  
- Contract Type  
- Billing  
- Rating  
- Age  
- Salary  
- Base Pay  
- Bonus  
- Unit Price  
- Volume  
- Opening Balance  
- Closing Balance  
- Low  
- Unit Sales  
- Total Sales  
- Months (Tenure)  
- Education  

### Key Details

- Missing values found in **Base Pay**, **Opening Balance**, and **Total Sales**  
- Handled using **KNN Imputer**  
- Final cleaned dataset contains **zero missing values**

---

## Data Preparation

Steps performed:

- Loaded CSV and verified data shape (**5000 × 20**)  
- Identified columns with missing values  
- Imputed missing values using **KNN Imputer**  
- Applied **Label Encoding** to categorical features  
- Checked variable distributions using boxplots  
- Removed outliers using the **IQR method**  
- Performed **Spearman correlation** for feature selection  

---

## Analysis & Visualizations

### 1. Gender Distribution

- Male: **2528**  
- Female: **2472**  
Employee distribution is nearly equal.

### 2. Education Breakdown

- PG: 2979  
- Graduation: 1980  
- Intermediate: 27  
- High School: 14  

### 3. Contract Type Distribution

- Month-to-Month: 2777  
- Two Year: 1195  
- One Year: 1028  

### 4. Salary Distribution & Outliers

- Boxplots used to inspect Salary, Base Pay, Bonus, etc.  
- Significant outliers identified and removed.

### 5. Salary Correlations

Spearman correlation revealed:

- **Total Sales → Salary: 0.99** (near perfect monotonic relation)  
- Bonus, Base Pay, Unit Sales also highly correlated (**> 0.8**)  

These became major predictors for modeling.

### 6. Numerical Feature Relationships

Scatter plots showed:

- Higher Total Sales → Higher Salary  
- Higher Bonus → Higher Salary  
- More Months of Experience → Higher Salary  

### 7. Categorical Impact on Salary

- PG employees earn: **₹50,000 – ₹2,00,000**  
- High School / Intermediate: **< ₹25,000**  
- Gender shows no meaningful salary difference.

### 8. Company Hiring Trends

- **765 hires** in the last four months  
- **269 employees** have long tenure (72 months)

---

## Machine Learning Models

Models trained after cleaning, encoding, scaling, and feature selection:

- **Linear Regression:** 78.27%  
- **Decision Tree Regression:** 99.35%  
- **Random Forest Regression:** 99.09%  
- **XGBoost Regression:** 99.24% (best performer)

### Cross-Validation Results

- Random Forest CV: **0.99993**  
- XGBoost CV: **0.99961**  

---

## Final Model

- **XGBoost Regressor** selected as final model  
- Normalized using **StandardScaler**  
- Model saved as: `hr.pkl`  
- Scaler saved as: `schr.pkl`  
- Deployed using both **Tkinter** and **Streamlit** interfaces  

---

## Key Insights

Salary is most strongly influenced by:

- Age  
- Education  
- Months of Experience  
- Total Sales  
- Performance Metrics  

Additional observations:

- Higher sales strongly increase salary  
- Education level affects salary brackets significantly  
- Gender has no major impact on salary  
- Strong correlations enabled highly accurate ML predictions  

---

## Technologies Used

- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- XGBoost  
- Seaborn  
- Matplotlib  
- Pingouin  
- Tkinter  
- Streamlit  

---

## How to Run the Project

### 1. Clone the repository
bash
```git clone https://github.com/yourusername/HRDataAnalytics.git```

### 2. Install dependencies
bash

Copy code

pip install pandas numpy matplotlib seaborn scikit-learn xgboost streamlit

### 3. Run the notebook
bash

Copy code

jupyter notebook HRDataAnalytics.ipynb

### 4. Launch the Streamlit App
bash

Copy code

streamlit run hrapp.py

## Future Improvements
- Integrate SHAP for model explainability

- Add HR attrition prediction module

- Create dashboards using PowerBI or Streamlit

- Add advanced feature importance visualizations

- Deploy as a complete web-based prediction system

## Contributing
Contributions are welcome.

Feel free to add new models, visualizations, or workflow improvements.

## Support
If you found this project helpful, consider starring the repository.
