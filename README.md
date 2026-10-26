# Telco Customer Churn Analysis & Prediction

**Customer Churn Analysis, Machine Learning Prediction, and Risk-Based Retention Strategies**

## 1. Project Overview

Customer churn is a major challenge in the telecommunications industry, as losing existing customers can affect business revenue and long-term growth. This project develops an end-to-end customer churn analysis and prediction workflow using Python, machine learning, and Power BI. The analysis aims to identify key factors associated with customer churn, predict customers at risk of leaving, and develop risk-based retention recommendations to support business decision-making.

## 2. Business Problem

Telecommunication companies need to understand why customers leave and identify customers who are more likely to discontinue their services. This project addresses three key questions:

- What customer characteristics are associated with higher churn rates?
- How effectively can machine learning predict customer churn?
- How can predicted churn probabilities support customer retention strategies?

## 3. Project Objectives

- Analyze customer behavior and identify churn patterns through exploratory data analysis.
- Develop and compare machine learning classification models.
- Evaluate model performance and optimize the classification threshold.
- Segment customers based on predicted churn probabilities.
- Recommend retention strategies for different customer risk levels.
- Build interactive Power BI dashboards to communicate analytical findings.

## 4. Dataset

This project uses the **IBM Telco Customer Churn** dataset, containing 7,043 customer records. The dataset includes customer demographics, subscription information, service usage, billing details, and churn status. The target variable is `Churn`, indicating whether a customer discontinued their service.

## 5. Tools & Technologies

- **Python:** Data analysis and machine learning
- **Pandas & NumPy:** Data cleaning and manipulation
- **Matplotlib & Seaborn:** Data visualization
- **Scikit-learn:** Preprocessing, model training, and evaluation
- **XGBoost:** Gradient boosting classification
- **Power BI:** Interactive dashboard development
- **Jupyter Notebook:** Analysis documentation

## 6. Project Workflow

**Data Cleaning → Exploratory Data Analysis → Machine Learning Modeling → Model Evaluation → Risk Segmentation → Business Recommendations → Power BI Dashboards**

## 7. Exploratory Data Analysis

The exploratory analysis identified several patterns associated with customer churn:

- **Overall Churn Rate:** 26.54% of customers discontinued their services.
- **Contract Type:** Month-to-month customers had the highest churn rate at 42.71%.
- **Customer Tenure:** Customers with 0–12 months of tenure had a churn rate of 47.44%.
- **Monthly Charges:** Customers in the high monthly charges category had a churn rate of 37.80%.
- **Internet Service:** Fiber optic customers had a churn rate of 41.89%.

These findings indicate that contract type, tenure, monthly charges, and internet service type are important factors to consider when analyzing customer churn.

## 8. Machine Learning Modeling

Three classification algorithms were evaluated:

- Logistic Regression
- Random Forest
- XGBoost

The models were compared using stratified 5-fold cross-validation.

### Cross-Validation Performance

| Model | ROC-AUC |
|---|---|
| Logistic Regression | 0.846 |
| Random Forest | 0.836 |
| XGBoost | 0.849 |

**XGBoost** achieved the highest cross-validation ROC-AUC and was selected as the final model.

### Final Model Performance

After classification threshold optimization, the selected threshold was **0.35**.

| Metric | Test Result |
|---|---|
| Accuracy | 77.50% |
| Precision | 55.90% |
| Recall | 72.19% |
| F1-Score | 63.01% |
| ROC-AUC | 0.846 |

The model identified approximately 72% of actual churned customers in the test set, providing a foundation for customer risk identification.

## 9. Customer Risk Segmentation

Customers were segmented into three risk levels based on their predicted churn probabilities.

| Risk Level | Churn Probability | Customer Distribution |
|---|---|---|
| Low Risk | ≤30% | 61.53% |
| Medium Risk | >30%–70% | 29.95% |
| High Risk | >70% | 8.52% |

Risk segmentation was performed on **1,409 customers in the test set**.

These thresholds were defined as initial business rules to support retention prioritization.

## 10. Business Recommendations

Retention strategies were developed based on customer risk categories.

| Risk Level | Recommended Strategy |
|---|---|
| High Risk | Offer long-term contract incentives |
| Medium Risk | Implement customer engagement and loyalty programs |
| Low Risk | Maintain regular customer service and support |

High-risk customers should receive greater attention from retention teams, particularly customers with shorter tenure, higher monthly charges, and month-to-month contracts.

These strategies are rule-based recommendations and have not yet been validated through actual retention campaigns.

## 11. Power BI Dashboards

Two interactive dashboards were developed to communicate the analytical results.

### Dashboard 1 — Customer Churn Overview

This dashboard provides an overview of customer characteristics, churn distribution, and factors associated with customer churn.

<img width="1082" height="742" alt="image" src="https://github.com/user-attachments/assets/d7bc63d1-09ef-403f-bf39-346644d4c19c" />

### Dashboard 2 — Churn Prediction & Retention Strategy

This dashboard presents machine learning predictions, customer risk segmentation, and recommended retention strategies based on the test dataset.

<img width="1082" height="741" alt="image" src="https://github.com/user-attachments/assets/d76092f4-5841-42b7-881a-2dc7370421ca" />

## 12. Project Structure

Organize the repository into separate folders for datasets, notebooks, dashboards, and supporting documentation. Include a `requirements.txt` file to document Python dependencies.

## 13. How to Run

1. Clone the GitHub repository.
2. Install dependencies using `pip install -r requirements.txt`.
3. Run the notebooks in order:
   - `01_EDA.ipynb`
   - `02_Modeling.ipynb`
   - `03_Business_Recommendations.ipynb`
4. Open the Power BI dashboard files to explore the visualizations.

Ensure dataset paths are configured correctly before running the notebooks.

## 14. Project Limitations

- The model was trained and evaluated using a historical telecommunications dataset.
- Risk segmentation thresholds have not been optimized based on business costs or customer lifetime value.
- Retention recommendations have not been tested through real-world campaigns.
- Additional validation is required before implementing the model in a production environment.

## 15. Conclusion

This project demonstrates how exploratory data analysis, machine learning, and business intelligence can be integrated into an end-to-end customer retention workflow. The results provide insights into customer churn patterns and establish a data-driven approach for identifying at-risk customers and prioritizing retention efforts.
