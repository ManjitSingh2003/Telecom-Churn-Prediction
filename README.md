# Telecom Churn Prediction Project

## Overview

In this project, we aim to analyze customer behavior in the telecommunications industry to predict churn, specifically focusing on high-value customers. Customer churn is a major concern in the telecom sector, where customer retention is more cost-effective than acquisition. This project leverages a dataset from a leading telecom firm, encompassing customer-level data over a period of four months. The primary goal is to predict whether a high-value customer will churn in the fourth month, based on their usage behavior in the previous three months.

### Key Objectives:
1. *Predict Churn*: To predict customers likely to churn using various machine learning models.
2. *Identify Key Indicators*: To understand the primary drivers of customer churn, enabling the company to take proactive measures.
3. *Handle Class Imbalance*: Since churn is an infrequent event, techniques to handle class imbalance are incorporated in the modeling process.
4. *Dimensionality Reduction*: Principal Component Analysis (PCA) is applied to reduce dimensionality and enhance model performance.

## Data Description

The dataset used for this analysis is too large to be hosted directly in this repository. You can download the dataset from the following Google Drive link:

(**Dataset Download Link**)[https://drive.google.com/file/d/1SWnADIda31mVFevFcfkGtcgBHTKKI94J/view?usp=sharing]

The dataset consists of customer-level data for four months, represented as months 6 (June), 7 (July), 8 (August), and 9 (September). The first two months represent the “good” phase where customers are likely satisfied. The third month represents the “action” phase, where customer behavior may indicate dissatisfaction. The fourth month represents the “churn” phase, where the dataset identifies customers who have stopped using the service.

The key variables include:
- *Total Outgoing Minutes* (total_og_mou)
- *Total Incoming Minutes* (total_ic_mou)
- *2G/3G Data Usage* (vol_2g_mb, vol_3g_mb)
- *Recharge Information* (recharge_* variables)
- *Customer Demographics* (aon, age_on_network)

### Churn Definition:
- Customers who did not make any calls (incoming or outgoing) and did not use mobile data during the churn phase (month 9) are tagged as churners.

## Methodology

### Data Preprocessing:
- *Filtering High-Value Customers*: High-value customers are defined as those who have recharged with an amount greater than or equal to the 70th percentile of the average recharge value in the first two months.
- *Feature Engineering*: New features are derived to improve the prediction accuracy. For example, we calculate metrics such as average usage over multiple months.
- *Handling Missing Data*: Missing values are handled by imputing or removing records, depending on the distribution of missing data across columns.

### Modeling Techniques:
- *Principal Component Analysis (PCA)*: PCA is used to reduce the dimensionality of the dataset, focusing on the most significant features.
- *Classification Models*: Various models are tested, including Logistic Regression, Random Forest, and Gradient Boosting. Models are evaluated using performance metrics such as accuracy, precision, recall, and the area under the ROC curve (AUC-ROC).

### Class Imbalance Handling:
- *Oversampling*: Techniques such as Synthetic Minority Over-sampling Technique (SMOTE) are used to balance the minority (churn) class.
- *Evaluation Metric*: Since accurately identifying churners is the primary goal, precision and recall are prioritized over accuracy.

## Results and Interpretation

- The model performance is evaluated based on recall (i.e., the proportion of actual churners correctly identified). 
- The feature importance from models such as Random Forest helps identify the critical factors leading to customer churn.
- Based on the model, features like average data usage, recharge frequency, and call behavior are identified as strong indicators of churn.

## Recommendations

Based on the churn prediction results and feature importance, the telecom company can:
1. Offer targeted promotions to high-risk customers during the “action” phase.
2. Monitor key indicators such as reduced data usage or outgoing call frequency to intervene before customers churn.
3. Implement retention strategies like personalized recharge offers or improved service quality for the top 20% of customers.
