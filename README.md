# Terrorist Dataset

I really deveopled an interest in Machine learning after I got to read the book 
"Andreas C. Müller, Sarah Guido-Introduction to Machine Learning with Python_ A Guide for Data Scientists-O’Reilly Media (2016)".
The reason I chose this challenge is because it is a global phenomenon and a pressing issue worldwide and it gave me a chance to apply what I have learnt.


EDA:

In this challenge,the scope for EDA is less as all the information that can can be extracted are already given as Features.
eg:Latitude and Longitude.
	Using Geocoding,we could have extracted the information like Country, State etc.. but this information is already provided. Similarly, 
    applying text mining and regular expressions on SUMMARY Feature would have provided with the key information like dates.But, even this information is provided as features. 
    
Pre-Processing:



In the dataset, there are many features with missing values greater than 70%. Such Columns are dropped.


Also, there is only 1 row for some Target variable. In such cases,it might only be in test set and gets classified as another class which  brings down the evaluation metric.So, to avoid that those cases are oversampled by cloning the records.

To label the categorical variables, factorize the class labels.


Most of the variables remaining in the dataset are categorical variables.To deal with the missing values in the features, replace the missing values are replaced with their corresponding modes.   

Model selection:


RandomforestClassifier is used to classify the target variable. Other classifiers have some limitations like SVClassifier has scalibity issue where it is difficult to scale for datasets more than 10k rows.Logistic Regression works for this multi-class classification but accuracy will not be as much as Randomforest as this dataset is heavily imbalanced while this bias does not effect Randomforest model.
Generally, boosting models are more sensitive to bias than bagging models.
Boosting models like XGBoost and Gradient boosting wouldn't have be a good choice even though it improves the accuracy in some cases.

Evaluation metric:


Evaluation metrics used are Accuracy and roc-auc score for each class to show how the model is performing in predicting the classes.
And roc-auc is a good measure as it measures the sensitivity of classification. 


Improvements in mind to execute in future:

Model Validation:

Divide the dataset into train,validation and test sets so that I can validate on validation set and predict on test set.

Ensembling:


Even though Randomforest itself is an ensemble, using of other ensembling methods like stacking which uses different models to improve the accuracy and make a robust prediction.

The accuracy of 90% is acheived with Randomforest and can be further tuned for higher accuracy.
