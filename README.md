# FindDefault-Prediction-of-Credit-Card-fraud-

## Problem Statement: 
A credit card is one of the most used financial products to make online purchases and payments. Though the Credit cards can be a convenient way to manage your finances, they can also be risky. Credit card fraud is the unauthorized use of someone else's credit card or credit card information to make purchases or withdraw cash. It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase. The dataset contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions. We have to build a classification model to predict whether a transaction is fraudulent or not.

## Data Set:
The Data Set contains 284807 rows and 31 columns where to safeguard user identity and secure their confidential data, the dataset provider has used Principal Component Analysis to transform the original numerical features, compressing them into 28 principal components except columns Time, Amount and Class. The Class column is our target column which is going to be used for finding fraudulent(1) and non-fraudulent(0) transactions. 

## Data Cleaning:
While trying to clean the data from null and duplicate values we found out that there are no null values in data set but it did contain some duplicates.

## Exploratory Data Analysis:
We tried to find out the number of Fraudulent and non-fraudulent transactions in the data set and plotted the graph showing their relationship.
After getting the the number of Fraudulent and non-fraudulent transactions we tried to understand more about our data set particularly Time and Amount column. We also plotted the graph to know at which time most transactions took place and if outlier data was present in the Amount column.
We found out the percentage fraudulent transactions in the data set i.e 0.17 %.

## Feature Engineering:
Since, we didn’t need the Time and Amount column we dropped these 2 columns from our data set and added new column called scaled values. And for training we copied the data into 2 different variables X and Y. where X contained PCA components + Scaled amount and Y contained Class. 

## Model Training:
We splitted the credit card data into 70-30 using train_test_split(), where our parameters were:
• X : Feature Matrix 
• Y : Target Variable
We set the test_size to 0.3, meaning 30% of the data is allocated for the test set.

## Model Selection:
We selected the Decision Tree and Random Forest algorithms for our model. 
• A Decision Tree is a supervised learning algorithm that splits the dataset into subsets based on feature values, creating a tree-like structure of decisions. 
• Random Forest is an ensemble learning method that combines multiple decision trees to improve accuracy and prevent overfitting.
We found the score for each of the algorithm for finding which is better for our data.

## Model Validation:
We tried to validate and test our models based on various criterias such as accuracy_score , precision_score , recall_score , F1_score and confusion matix. We also plotted the heatmaps for each of the model’s confusion matix.

## Dealing with Imbalanced data:
This data set is highly imbalanced. The data should be balanced 
using the appropriate methods before moving onto model building.
The class imbalance problem can be solved by various techniques. 
We will use one such technique called Oversampling . 
The method through which oversampling is possible is called SMOT 
(Synthetic Minority Oversampling Technique or SMOTE).
We used Random forest algorithm on the resampled data as we 
found out that random forest is better than the Decision tree and calculated the score of random forest algorithm for sampled data.
Then we validated the resampled Random forest model based on various criterias such as accuracy_score , precision_score , recall_score , F1_score and confusion_matrix. We also plotted the heatmaps for each of the model’s confusion matix.

## Model Deployment:
To prepare for model deployment as part of future plans, we will use the pickle library to save both the dataframe and the model.
