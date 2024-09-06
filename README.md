# Feature-wise Model Segmentation: Predicting Credit Card Usage

Feature-wise model segmentation using XGBoost was implemented for this project. Separate models are trained for each unique user, enabling more targeted and accurate predictions compared to training a model on the entire dataset. 

## **Summary**

The objective of this project is to produce a model that can accurately predict whether or not a particular user, on a given day, is going to have a credit card tranaction in the next k-days. This project loads the raw dataset and, upon data cleaning, retains 89% of the original rows. Additionally, users must have made at least 2 transactions over 100 days, which further sheds another 3.2%. 

The model developed is infact a collection of 3578 XGBoost Classifiers assembled together. This ensemble approach works by training each individual model on a specific user's transaction data and developing predictions for that user. For k=5 and k=10, this approach significantly outperformed the naive baseline, Logistic Regression, and a single XGBoost Classifier trained on the entire dataset. 

## **Methodology**
* **Data Loading**: Load data from csv and clean the raw data
* **Data Preparation**: 
    * DataFrame: Produce a dataframe containing the daily history of each person and whether or not they had a transaction that day  
    * Target: Create a function that adds a target column, identifying for whether a given user on a particular day makes at least one transaction in the next k days (exclusive of the current day)
    * Feature Extraction: Extract additional features such as cumulative transactions, rolling transactions, Day of Week, etc., and apply One-hot-encoding to categorical variables   
* **ML Pipeline**: 
    Evaluate the following approaches
    *  Standard Approach: train a model (Logistic or XGBoost) on the dataset, obtain test predictions
    *  Ensemble Approach: Partition the dataset by each unique Person, train individual models on each subset, and collect all test predictions
        
* **Evaluation**: Identify the best performing approach based on several evaluation metrics.


## Contributors

The following individuals who have contributed to this project:

- Ian CoKehyeng
