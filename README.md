# Lead Scoring Case Study

## Overview
X Education, an online education company, aims to increase its lead conversion rate by identifying the most promising leads. The goal of this project was to build a logistic regression model that assigns a lead score between 0 and 100 to each lead. The higher the score, the more likely the lead is to convert. The CEO has set a target lead conversion rate of around 80%.

## Problem Statement
X Education receives many leads daily, but only about 30% convert into paying customers. To enhance efficiency, the company wants to focus on 'Hot Leads'—those with the highest conversion probability. By focusing on these leads, the company hopes to improve its overall conversion rate.

## Data
The dataset consists of approximately 9,000 entries with 34 feature variables and one target variable (`Converted`). The features include information like Lead Origin, Lead Source, Last Activity, and more.

## Data Cleaning and Preprocessing
- **Dropped Columns:** Removed columns with more than 35% missing values, redundant columns, and those with single values.
- **Missing Values:** Imputed missing values for categorical variables using the mode and for numerical variables using the median.
- **Outliers:** Performed capping on `TotalVisits` and `Page Views Per Visit` to handle outliers.
- **Feature Engineering:** Merged low-frequency categories and reduced the number of categories for several columns.

## Exploratory Data Analysis (EDA)
- **Conversion Rate:** Approximately 40% of the leads were converted, which was deemed acceptable for model building.
- **Key Insights:**
  - Most leads originated from the "Landing Page Submission" and "Google" sources.
  - Leads with "SMS Sent" as the last activity showed the highest conversion rate.
  - Unemployed individuals and those who didn't request a free copy of the course material were more likely to convert.

## Model Building
A logistic regression model was developed using Recursive Feature Elimination (RFE) for feature selection and then insignificant variables were eliminated based on p-value. The final model achieved:
- **Training Set:** 81% accuracy with a precision of 73.8% and recall of 78%.
- **Test Set:** 80.9% accuracy with a precision of 75% and recall of 75.9%.

## Optimal Cutoff
- **ROC-AUC Analysis:** The optimal cutoff point was determined to be 0.369, yielding a balance between sensitivity (75.9%) and specificity (84%).

## Key Findings
- Variables that significantly impact lead conversion include `Total Time Spent on Website`, `Total Visits`, and `Page Views Per Visit`.
- Lead Origin, Lead Source, and Last Activity are also important factors.
- Leads with a score of 36 or higher have a high likelihood of conversion, with conversion rates of 87% and above.

## Conclusion
The model provides a reliable scoring system that can help X Education focus on leads with a high probability of conversion, thereby improving their overall efficiency and conversion rate.
