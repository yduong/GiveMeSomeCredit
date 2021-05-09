1. Tell us how you validate your model, which, and why you chose such evaluation technique(s).
- I use AUC to validate the mode. It is because our data is very imbalanced and positive data should be as equally important
as negative data. AUC metric is a good option for that.

2. What is AUC? Why do you think AUC was used as the evaluation metric for such a problem? What are
other metrics that you think would also be suitable for this competition?
- AUC is the area under the curve. The curve is plotted by using the value of true positve rate and false positive rate of different threshold. The higher the value of AUC, the better the model. AUC take into consideration of both true positive rate and false positive rate. So for imbalanced dataset, if the model always predict the value of one side, AUC will be able to detect that. Because the data is imbalanced, AUC is a good metric to be used.
- In addition, we can use F1 score. F1 score will help to indicate if the model is able to have a good value of precision and recall, i.e: the model is able to detect positive data and detect true positive. 

3. What insight(s) do you have from your model? What is your preliminary analysis of the given dataset?
- From the preliminary analysis, data is very imbalanced, positive cases are only ~6.68%. ensemble or boosting method should be able to help overcome this issue. 
- We will evaluate: RandomForestClassifier, XGBClassifier and LogisticRegression
- For columns ['NumberOfTimes90DaysLate','DebtRatio','MonthlyIncome'], the ranges of the data are very large. Since the agorithm we use can take into account the different in the range of the data by using coef, we can ignore this issue
- For ouliers, using Boxplots to detect the outliners, we find that the number of outliners are more many (~10), so we can ignore the outliners. This also helps to increase the variance of our model

4. Can you get into the top 100 of the private leaderboard, or even higher?
The score I have from Kaggle is only: 0.82854