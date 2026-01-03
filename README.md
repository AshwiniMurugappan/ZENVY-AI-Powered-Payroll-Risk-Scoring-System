# ZENVY – AI-Powered Payroll Risk Scoring System 🛡️💰

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📋 Project Overview
This project was developed as a submission for the **ZENVY Data Science Internship** 

The goal was to engineer a **Payroll Risk Scoring System** that identifies high-risk records (potential fraud, clerical errors, or ghost employees) by analyzing attendance patterns, leave frequency, and salary fluctuations. By implementing this system, organizations can automate the audit process and ensure financial integrity before payroll execution.

---

## 🛠️ Technical Stack
* **Data Manipulation:** `Python (Pandas, NumPy)`
* **Modeling:** `Scikit-learn` (Random Forest, Logistic Regression, Gradient Boosting, XGBoosting)
* **Statistical Visualization:** `Python (Seaborn, Matplotlib)`

---

## 📊 Feature Engineering
The model was built using five primary behavioral features:
1.  **Attendance_Rate:** Percentage of days present (Behavioral Risk).
2.  **Leave_Frequency:** Total leaves in the last 6 months (Absenteeism Risk).
3.  **Salary_Change_Pct:** The percentage hike from the last pay cycle (Anomaly Risk).
4.  **Experience_Years:** Tenure of the employee.
5.  **Overtime_Hours:** Manually entered extra hours (Clerical Risk).

---

## 🔬 Model Comparison & Performance
I evaluated four models to find the most robust solution for detecting payroll anomalies. In a payroll context, **Recall** is our most critical metric, as we cannot afford to miss a high-risk record.

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Random Forest** | **0.90** | **1.00** | **0.50** | **0.66** | **1.00** |
| **Gradient Boosting** | 0.90 | 1.00 | 0.50 | 0.66 | 1.00 |
| **Logistic Regression** | 0.90 | 1.00 | 0.50 | 0.66 | 0.93 |
| **XGBoost** | 0.80 | 0.50 |	0.50 | 0.50 |	0.87 |

### **Mathematical Justification**
The **Random Forest Classifier** was selected for the final implementation. Unlike linear models, Random Forest uses **Recursive Partitioning** to capture non-linear interactions between features (e.g., a risk triggered only when *both* low attendance and high salary jumps occur). By using **Bagging (Bootstrap Aggregating)**, the model reduces variance and prevents overfitting, making it highly reliable for identifying the 20% of anomalous records in our dataset.

---

## 💡 Key Insights
The **Feature Importance Analysis** shows that **Salary_Change_Pct (38.8%)** and **Attendance_Rate (30.6%)** are the most significant drivers of payroll risk. 



- **Anomalous Hikes:** Salary jumps exceeding 30% were the primary reason for a record being flagged.
- **Ghost Employee Detection:** Employees with high salary changes but low attendance rates were assigned a Risk Score > 85%.

---

## 🚀 Installation & Usage
1.  **Clone the Repo:**
    ```bash
    git clone [https://github.com/AshwiniMurugappan/ZENVY-AI-Powered-Payroll-Risk-Scoring-System.git](https://github.com/AshwiniMurugappan/ZENVY-AI-Powered-Payroll-Risk-Scoring-System.git)
    ```
2.  **Install Dependencies:**
    ```bash
    pip install pandas scikit-learn matplotlib seaborn
    ```
3.  **Run the Predictor:**
    ```python
    # Load your trained model and run on new payroll data
    predictions = best_model.predict(new_payroll_data)
    ```

---

## 📂 Project Structure
* `zenvy_payroll_risk.csv`: The enhanced dataset including risk features.
* `payroll_analysis.ipynb`: The full EDA and modeling notebook.
* `README.md`: Project documentation.

---

## 👤 Author
**[Ashwini Murugappan]**
* Data Science Intern Aspirant
* [[LinkedIn Profile Link](https://www.linkedin.com/in/ashwini-murugappan-739aa5159/)]
* [[Portfolio Link](https://github.com/AshwiniMurugappan/)]
