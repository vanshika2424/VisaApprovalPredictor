
# VisaApprovalPredictor

## Overview
This project aims to automate and enhance the U.S. visa certification process using a machine learning-based classification model. By leveraging historical data from the Office of Foreign Labor Certification (OFLC), the model predicts the likelihood of a visa application being certified or denied, helping streamline decision-making and reduce manual workload.

## Problem Statement
In FY 2016, the OFLC processed over 775,000 employer applications for nearly 1.7 million positions. With application volumes increasing annually, manual review has become inefficient. This project provides a data-driven solution to assist in evaluating visa applications more efficiently and fairly.

## Objectives
- Predict the outcome (`Certified` or `Denied`) of visa applications
- Identify key drivers influencing visa decisions
- Recommend a high-performing model for potential deployment

## Approach
- Performed data cleaning, encoding, and transformation
- Addressed class imbalance using oversampling techniques
- Evaluated multiple classifiers: Gradient Boosting, XGBoost, AdaBoost, Random Forest
- Selected the best model based on validation and test metrics

## Final Model: XGBoost (with Oversampled Data)

**Test Set Performance:**

| Metric     | Value   |
|------------|---------|
| Accuracy   | 0.7595  |
| Recall     | 0.8748  |
| Precision  | 0.7884  |
| F1 Score   | 0.8293  |

XGBoost was chosen as the final model due to its high recall and balanced F1-score, making it suitable for deployment in real-world decision-making scenarios.

## Dataset Description

The dataset includes attributes related to both employees and employers involved in visa applications.

### Feature Summary:

| Column Name              | Description |
|--------------------------|-------------|
| `case_id`                | Unique ID of each visa application |
| `continent`              | Continent of origin of the employee |
| `education_of_employee`  | Education level of the employee |
| `has_job_experience`     | Whether the employee has prior job experience (`Y` / `N`) |
| `requires_job_training`  | Whether the employee requires job training (`Y` / `N`) |
| `no_of_employees`        | Number of employees in the employer's company |
| `yr_of_estab`            | Year the employer's company was established |
| `region_of_employment`   | Intended region of employment within the U.S. |
| `prevailing_wage`        | Average wage offered, based on occupation and location |
| `unit_of_wage`           | Wage unit (`Hourly`, `Weekly`, `Monthly`, `Yearly`) |
| `full_time_position`     | Whether the position is full-time (`Y`) or part-time (`N`) |
| `case_status`            | Target variable – visa application outcome (`Certified` / `Denied`) |

## Repository Contents
- `VisaApproval.ipynb`: Main Colab notebook containing data exploration, preprocessing, model training, evaluation, and comparison
- Dataset: `EasyVisa.csv` (uploaded locally for model training)
- Visuals and performance metrics for all models evaluated

