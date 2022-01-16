# Credit-Card-Fraud-Prediction

Credit card fraud is a major concern in the financial industry nowadays. Analysing fraudulent transactions manually is unfeasible due to huge amounts of data and its complexity. However, given sufficiently informative features, one could expect it is possible to do using Machine Learning.

### Data Description

The datasets contains transactions made by credit cards in September 2013 by european cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.It contains only numerical input variables which are the result of a PCA transformation. Due to confidentiality issues, there are not provided the original features and more background information about the data.

* Features V1, V2, ... V28 are the principal components obtained with PCA;
* The only features which have not been transformed with PCA are Time and Amount. Feature Time contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature Amount is the transaction Amount, this feature can be used for example-dependant cost-senstive learning.
* Feature Class is the response variable and it takes value 1 in case of fraud and 0 otherwise.


### Exploratory Data Analysis
<img src="images/class_labels.png?raw=true"/>

<img src="images/tdd_transactions.png?raw=true"/>

<img src="images/amount.png?raw=true"/>

<img src="images/average.png?raw=true"/>



### Modeling and Performance 
The extreme unbalancing may cause to obtain over 99 % accuracy even if the model is a simple null classifier which always predict Class as 0. Means, it is insensitive towards false negatives. So measuring the model with accuracy score should not be used here. Rather, the most appropriate performance measures for this task are precision, recall, f1-score and auc score. I have used auc score as a main concern. To deal with this imbalanced dataset, I have used a sampling technique called SMOTE (Synthetic Minority Over-sampling Technique).

Simple Logistic regression was enough to give satisying performance since the data imbalancing has been treated already using SMOTE. avaerage metircs are as (for 5 validations): 

* accuracy = 0.97
* recall = 0.96 
* precision = 0.97
* auc score = 0.97


### Comments
Credit card fraud detection is being a main concern nowadays. Even if the chosen data set is old, and varibales are anonymous, it is possible to apply same logics for a new data set. Because, for this particular problem main concern is imbalanced data. Since fraud is very less compared to the genuine transactions, any bank can provide only a highly imbalanced data, and this work demonstrates a nice solution for that. Variables depending the prediction of fraud may vary for each bank and using some domain knowledge and the PCA technique, it is possible to have a well structured dataset. 

For code, visit :[Notebook for credit card fraud prediction](https://github.com/MuafiraThasni/Credit-Card-Fraud-Prediction/blob/main/credit_card_note.ipynb/).
