# Small Business Loans: Predicting Default
Analyzing historical data to create the best model predicting if a loan will default or not. 

The original data was taken from Kaggle, and can be found here: https://www.kaggle.com/mirbektoktogaraev/should-this-loan-be-approved-or-denied?select=SBAnational.csv

A description of the SBA loan program can be found here: https://www.sba.gov/offices/headquarters/ofa/resources/11421

### Important notes
The data cleaning notebook does not need to be executed to run the models. The cleaned data have been saved off and included in the repo. There are two versions, and models were built on both. The seocnd cleaning data are more suited to the problem and addressed some cleaning/encoding errors.

The modeling notebook takes ~15 minutes to complete. A gradient boosting classifier was the best performer against logistic regression and random forest. Downsampling was used on the negative class to increase recall, sacrificing precision.
