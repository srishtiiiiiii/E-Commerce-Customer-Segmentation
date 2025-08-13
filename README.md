# E-Commerce Customer Segmentation and Churn Prediction

## 📈 Customer Churn Prediction using RFM & Logistic Regression
This is a comprehensive analysis of the Olist e-commerce dataset to predict customer churn. The project leverages RFM (Recency, Frequency, Monetary) analysis for feature engineering and builds an interpretable Logistic Regression model to identify at-risk customers.

## 🎯 Project Goal
The primary objective is to build a model that can accurately predict which customers are likely to churn. This involves:

🧹 Processing and cleaning a large, multi-table e-commerce dataset.

🛠️ Engineering meaningful features using RFM analysis to capture customer behavior.

📊 Performing exploratory data analysis (EDA) to uncover patterns related to churn.

🤖 Building and evaluating a machine learning model to predict churn.

🧠 Interpreting the model results to understand the key drivers of customer churn.

## 💾 Dataset
This analysis uses the public Olist E-commerce Dataset, which contains information on 100,000 orders from 2016 to 2018 in Brazil.

The following data files are used in this project:

olist_customers_dataset.csv

olist_orders_dataset.csv

olist_order_items_dataset.csv

olist_order_payments_dataset.csv

olist_products_dataset.csv

olist_sellers_dataset.csv

product_category_name_translation.csv

## 🚀 Analysis Pipeline
The project follows a structured approach from data ingestion to model interpretation.

Data Loading & Merging: All CSV files are loaded and merged into a single comprehensive DataFrame.

Data Cleaning: The dataset is filtered for delivered orders, and date columns are converted to the proper datetime format.

Feature Engineering & Churn Definition:

RFM Features are calculated for each unique customer:

Recency: Days since the last purchase.

Frequency: Total number of orders.

Monetary: Total amount spent.

Churn Definition: A customer is labeled as churned if their last purchase was more than 180 days ago.

Exploratory Data Analysis (EDA): Key relationships between customer behavior and churn are visualized. See plots in churn.ipynb output.

Model Preparation:

The dataset is split into 80% training and 20% testing sets.

Features are scaled using StandardScaler.

class_weight='balanced' is applied to handle the imbalanced nature of the churn data.

Model Training: A Logistic Regression model is trained on the prepared data.

Model Evaluation: The model's performance is rigorously tested using a classification report, confusion matrix, and ROC-AUC curve.

## 📊 Model Performance & Key Findings
The model achieved perfect accuracy on the test set, highlighting a strong—and expected—relationship between the engineered features and the churn definition.

Metric Score
Accuracy - 1.00

Precision -	1.00

Recall - 1.00

F1-Score - 1.00

ROC-AUC Score -	1.00

### Feature Importance
The model's coefficients show that recency is the single most important factor in predicting churn, which is logical given our churn definition.

### Feature	Importance Coefficient
recency	- 35.93

frequency	- 0.004

monetary - -0.012

The perfect score is a direct consequence of defining churn based on a recency threshold of 180 days. The logistic regression model easily learned this linear boundary. While this confirms the validity of the analysis, a real-world model would benefit from more diverse features.

