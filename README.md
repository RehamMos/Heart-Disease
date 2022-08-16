# Heart-Disease
Saving peoples’ lives is a vital topic so, trying to predict early heart disease injuries has a lot of interest. I preferred to work on health care dataset even if it is for learning because it enables me stay connected with real cases that one day I will face. Our problem is about heart disease, zero indicated that person does not have a disease, 1 indicates that person has a disease.
# Data Table
|Rows|Columns|  Duplications | Null values  |  Missing vales |
|----|-------|---------------|--------------|----------------|
|303 |  13   |No duplications|No Null values|No missing value|
|Data is balanced ant not linear, so rbf kernel of SVM will be used. Based on visualizing using seaborn|

# Models used 
I used SVM, KNN and Logostic regression (LR) with different split(25/75) and (30/70)
I tested in different cases using different feature selection(wrapper method) forward and backward and without selecting any feature using stratified kfold and without it to determine which case we get high accuracy and recall.
Recall in our case means how many people who algorithm predicted as they don’t have a disease and they actual have a disease. So, minimizing FN in our case is important.
## Results (splitting 30/70)
|Algorithm|    way used         | 0 / 1 |Recall|  Fscore  | 
|---------|---------------------|-------|------|----------|
|   LR    | No feature selection|   0   | 0.76 |  0.79    |
|   LR    | No feature selection|   1   | 0.88 |  0.85    |
|   LR    |Backward #columns=6  |   0   | 0.76 |  0.77    |
|   LR    |Backward #columns=6  |   1   | 0.82 |  0.81    |
|   LR    |Forward #columns=6   |   0   | 0.78 |  0.77    |
|   LR    |Forward #columns=6   |   1   | 0.80 |  0.81    |
|   SVM   |No feature selection |   0   | 0.100|  0.62    |
|   SVM   |No feature selection |   1   | zero |  zero    |
|   SVM   |Backward #columns=6  |   0   | 0.76 |  0.77    |
|   SVM   |Backward #columns=6  |   1   | 0.82 |  0.81    |
|   SVM   |Forkward #columns=6  |   0   | 0.78 |  0.78    |
|   SVM   |Forkward #columns=6  |   1   | 0.82 |  0.82    |
| KNN N=7 |No feature selection |   0   | 0.83 |  0.82    |
| KNN N=7 |No feature selection |   1   | 0.84 |  0.85    |
| KNN N=7 |Backward #columns=6  |   0   | 0.83 |  0.78    |
| KNN N=7 |Backward #columns=6  |   1   | 0.76 |  0.80    |
| KNN N=7 |Forward #columns=6   |   0   | 0.78 |  0.74    |
| KNN N=7 |Forward #columns=6   |   1   | 0.74 |  0.77    |
## Results (splitting 25/75)
|Algorithm|    way used         | 0 / 1 |Recall|  Fscore  | 
|---------|---------------------|-------|------|----------|
|   LR    | No feature selection|   0   | 0.77 |  0.82    |
|   LR    | No feature selection|   1   | 0.90 |  0.86    |
|   LR    |Backward #columns=6  |   0   | 0.80 |  0.81    |
|   LR    |Backward #columns=6  |   1   | 0.85 |  0.84    |
|   LR    |Forward #columns=6   |   0   | 0.80 |  0.81    |
|   LR    |Forward #columns=6   |   1   | 0.85 |  0.84    |
|   SVM   |No feature selection |   0   | 1    |  0.63    |
|   SVM   |No feature selection |   1   | zero |  zero    |
|   SVM   |Backward #columns=6  |   0   | 0.83 |  0.84    |
|   SVM   |Backward #columns=6  |   1   | 0.88 |  0.87    |
|   SVM   |Forkward #columns=6  |   0   | 0.80 |  0.85    |
|   SVM   |Forkward #columns=6  |   1   | 0.93 |  0.88    |
| KNN N=7 |No feature selection |   0   | 0.86 |  0.86    |
| KNN N=7 |No feature selection |   1   | 0.88 |  0.88    |
| KNN N=7 |Backward #columns=6  |   0   | 0.77 |  0.79    |
| KNN N=7 |Backward #columns=6  |   1   | 0.85 |  0.83    |
| KNN N=7 |Forward #columns=6   |   0   | 0.80 |  0.80    |
| KNN N=7 |Forward #columns=6   |   1   | 0.83 |  0.83    |

* Recall in our case means quantity of people who algorithm predicted as they don’t have a disease and they actual have a disease. So, minimizing FN in our case is important.

* I will choose SVM with forward (25/75) results >> because it gives me low FN which it is my target to minimize, highest F score and recall. 
Because of data size (303 rows and 13 columns) there is a probability that algorithm trained with data like in the test so, test accuracy is higher than training. As happened in SVM (forward, and backward) and KNN(No features selected) splitting 25/75
* Splitting data with (30/70) for algorithms (SVM without any feature selection) is a disaster FN & FP(50 & zero) and splitting also (27/75) is a disaster & FP(41 & 35). It is overfitting.
* Splitting data with (30/70) with different algorithms and with various feature selection ways is not the suitable way to get high F score. (I got high FN & FP).
* I found there is overfiting as mentioned in previous tables for most of algorithms. After applying Kfold cross validation, no changes happened for the result as it is one of ways to deal with overfitting.
