# Terrorist Dataset
EDA:

In this challenge,the scope for EDA is less as all the information that can can be extracted are already given as Features.
eg:Latitude and Longitude.
	Using Geocoding,we could have extracted the information like Country, State etc.. but this information is already provided. Similarly, 
    applying text mining and regular expressions on SUMMARY Feature would have provided with the key information like dates.But, even this information is provided as features. 
    
Pre-Processing:



In the dataset, there are many features with missing values greater than 70%. Such Columns are dropped.


Also, there is only 1 row for some Target variable. In such cases,it might only be in test set and gets classified as another class which  brings down the evaluation metric.So, to avoid that I've appended such rows couple of times so that when we split the dataset we have atleast one row for each class in both test and train.


To label the categorical variables, factorize the class labels.


Most of the variables remaining in the dataset are categorical variables.To deal with the missing values in the features, replace the missing values are replaced with their corresponding modes.   

Model selection:


RandomforestClassifier is used to classify the target variable. Other classifiers have some limitations like SVClassifier has scalibity issue where it is difficult to scale for datasets more than 10k rows.Logistic Regression works for this multi-class classification but accuracy will not be as much as Randomforest as this dataset is heavily imbalanced while this bias does not effect Randomforest model.

Evaluation metric:


Evaluation metric used is Accuracy and roc-auc score for each class to show how the model is performing in predicting the classes. 

Due to Memory constraints,I am unable to run GridsearchCV on Randomforest parameters. Similarly, I couldn't run XGboost aswell.But, XGboost would have improved the score.
