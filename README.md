# Linear Regression Analysis for E-commerce Customer Behavior

## Project Overview
This project analyzes customer behavior data from an e-commerce platform to determine whether the company should focus on improving its mobile app or website experience. The dataset includes metrics such as session length, time spent on the app/website, length of membership, and yearly spending. A linear regression model is used to identify key drivers of customer spending.

---

## Dataset
**Source**: [Kaggle E-commerce Customer Data](https://www.kaggle.com/iyadavvaibhav/ecommerce-customer-device-usage)  
**Features**:
- `Avg. Session Length`: Average duration of in-store advice sessions.
- `Time on App`: Average time spent on the app (minutes).
- `Time on Website`: Average time spent on the website (minutes).
- `Length of Membership`: Customer membership tenure (years).
- `Yearly Amount Spent`: Total yearly spending by the customer.

---

## Setup
### Dependencies
- Python 3.x
- Libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`

Install requirements:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### Load the Data
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load the dataset
customers = pd.read_csv('Ecommerce Customers.csv')
```

---

## Exploratory Data Analysis (EDA)

### Initial Data Inspection
```python
customers.head()  # Preview the first 5 rows
customers.info()  # Check data types and missing values
customers.describe()  # Summary statistics
```

### Key Visualizations
1. **Time on App vs. Yearly Spending**  
   A joint plot reveals a moderate positive correlation between time spent on the app and yearly spending.

   ```python
   sns.jointplot(x='Time on App', y='Yearly Amount Spent', data=customers, alpha=0.5)
   ```

2. **Time on Website vs. Yearly Spending**  
   No strong correlation observed, suggesting the website experience may not significantly impact spending.

3. **Pairplot Analysis**  
   The strongest correlation exists between `Length of Membership` and `Yearly Amount Spent`.

   ```python
   sns.pairplot(customers)
   ```

---

## Key Findings
1. **Mobile App Focus**: Time spent on the app shows a clearer correlation with customer spending compared to the website. Improvements to the app experience could drive higher revenue.
2. **Membership Value**: Long-term members tend to spend more, highlighting the importance of customer retention strategies.
3. **Website Optimization**: While the website is less correlated with spending, it remains critical for initial customer engagement and app downloads.

---

## Conclusion
The analysis suggests prioritizing **mobile app enhancements** to boost customer spending. Additionally, fostering long-term membership through loyalty programs could further increase revenue. The website should maintain usability but may not require immediate major investments.

---

Exploratory Data Analysis (EDA)
1. Feature Relationships
Pair Plot
![téléchargement1](https://github.com/user-attachments/assets/7a4480f4-999c-4650-8eb4-066418a24133)

Visualizes relationships between key metrics: Session Length, Time on App/Website, Membership Tenure, and Yearly Spending.

3. Membership Impact
Membership vs. Spending
![téléchargement](https://github.com/user-attachments/assets/54d3ff89-5dae-4011-be1f-7cfd09ac72aa)

Shows a strong positive correlation between membership duration and yearly spending.

Model Evaluation
3. Prediction Accuracy
Actual vs. Predicted Spending
![téléchargement (1)](https://github.com/user-attachments/assets/9b354e9f-d54c-47a1-a81f-cd35e317fb84)


Model predictions closely follow actual values, indicating good regression performance (points align near the diagonal).

4. Residual Analysis
Probability Plot
Residuals follow the theoretical quantile line, confirming normality assumptions for the linear regression model.
![téléchargement (2)](https://github.com/user-attachments/assets/404e200c-63d3-4596-8eff-30a152797fc2)

Key Insights
Membership Value: Longer membership strongly correlates with higher spending (Image 2).

App Impact: Time on the app shows moderate correlation with spending (visible in Image 1).

Model Validity: Residual normality (Image 4) and prediction alignment (Image 3) validate the regression approach.
