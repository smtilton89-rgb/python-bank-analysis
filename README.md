# python-bank-analysis

# UCI Bank Marketing – Customer Profile & Modeling (Python)

## Overview
This project analyzes the UCI **Bank Marketing** dataset to understand what customer characteristics and campaign factors are associated with subscribing to a term deposit. 
The notebook includes exploratory analysis (customer profiling) and a lightweight, interpretable classification model (logistic regression), evaluated using ROC/AUC.

## Dataset
Source: UCI Machine Learning Repository – Bank Marketing (Dataset ID: 222)  
The dataset contains direct marketing campaign outcomes from a Portuguese bank. The target variable `y` indicates whether the client subscribed to a term deposit (`yes`/`no`).

## Project Goals
- Build a clear customer profile of who is more likely to subscribe
- Explore relationships between key features (age, balance, job, marital status) and subscription outcome
- Train a logistic regression model as a simple, interpretable baseline
- Evaluate model discrimination using an ROC curve and AUC

## Tools & Libraries
- Python (pandas, numpy)
- matplotlib / seaborn
- scikit-learn (train/test split, logistic regression, ROC/AUC)
- ucimlrepo (dataset fetching)

## Key Steps
1. **Data Loading**
   - Dataset pulled using `ucimlrepo.fetch_ucirepo(...)`
   - Features and target combined into a single DataFrame

2. **Data Preparation**
   - Target `y` mapped to binary (yes=1, no=0)
   - Categorical features one-hot encoded using `pd.get_dummies`
   - Numeric features standardized to improve convergence (StandardScaler)

3. **Exploratory Analysis (Customer Profile)**
   - Distribution and imbalance check for `y`
   - Subscription rate comparisons across customer categories
   - Numeric distributions (age, balance) compared by outcome

4. **Modeling**
   - Logistic Regression baseline model
   - Evaluation using classification report + ROC curve
   - AUC reported as the primary summary metric (due to class imbalance)

## Notes on Class Imbalance
The target is imbalanced. Because of this, accuracy alone is not a meaningful metric; ROC/AUC and class-specific precision/recall provide better insight.

## Results Summary
- AUC: 0.6408
- Key drivers observed in EDA: Age and Marital Status affect subscriptions substancially
