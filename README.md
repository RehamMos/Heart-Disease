# Heart-Disease
Saving peoples’ lives is a vital topic so, trying to predict early heart disease injuries has a lot of interest. I preferred to work on health care dataset even if it is for learning because it enables me stay connected with real cases that one day I will face. Our problem is about heart disease, zero indicated that person does not have a disease, 1 indicates that person has a disease.
### Rows  303
### Columns  13
### Duplications   No duplications
### Null values No Null values
### Missing values?  No missing value
### Data is balanced ant not linear, so rbf kernel of SVM will be used. Based on visualizing using seaborn(mentioned in preprocessing section).
### I used SVM, KNN and Logostic regression (LR) with different split(25/75) and (30/70)
### I tested in different cases using different feature selection(wrapper method) forward and backward and without selecting any feature using stratified kfold and without it to determine which case we get high accuracy and recall.
### Recall in our case means how many people who algorithm predicted as they don’t have a disease and they actual have a disease. So, minimizing FN in our case is important.
### I will choose SVM with forward (25/75) results >> because it gives me low FN which it is my target to minimize, highest F score and recall. Because of data size (303 rows and 13 columns) there is a probability that algorithm trained with data like in the test so, test accuracy is higher than training. As happened in SVM (forward, and backward) and KNN(No features selected) splitting 25/75
### Splitting data with (30/70) for algorithms (SVM without any feature selection) is a disaster FN & FP(50 & zero) and splitting also (27/75) is a disaster & FP(41 & 35). It is overfitting.
### Splitting data with (30/70) with different algorithms and and with various feature selection ways is not the suitable way to get high F score. (I got high FN & FP).
### I found there is overfiting for most of algorithms. After applying Kfold cross validation, no changes happened for the result as it is one of ways to deal with overfitting.
