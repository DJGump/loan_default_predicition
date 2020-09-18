# Small Business Loans: Predicting Default
By predicting if a loan will default, the Small Business Administration (SBA) can better determine which loans need their support.

##### Contents
* 2 Jupyter notebooks, for data cleaning and modeling
* A PDF slide deck, being the standalone synthesis of the project
* A README (You are here. Thank you.)
* Various figure files used in the slides
* A data folder, containing my cleaned data and source documentation.

My original data was taken from Kaggle, and can be found [here](https://www.kaggle.com/mirbektoktogaraev/should-this-loan-be-approved-or-denied?select=SBAnational.csv). This is historical data from the SBA, assembled and distributed as a teaching tool for aspiring bankers. By approaching the dataset form the perspective of the SBA, I was able to create and solve new problems, namely by focusing on capturing more of the defaulted loans and potentially enabling taking on risk. The SBA exists to help businesses, so they may want to prioritize insuring loans that would not be granted without their support, even if it is likely that loan will default and result in a payout from the SBA. Likewise, recall was maximized with a gradient boosting classifier, reaching 95%. There is no harm to a business if it is denied support because of an incorrect prediction of default; the loan ends up paid. However, if there are a limited number of commitments to give, too many businesses may receive SBA backing who ended up not needing it. If the model proves valid in the wild, the scoring metrics can help determine the expected percentage to default. If you are the SBA, I would appreciate your feedback. 

A description of the SBA loan program can be found [here](https://www.sba.gov/offices/headquarters/ofa/resources/11421)

### Notes About the Code
The data cleaning notebook does not need to be executed to run the models. The cleaned data have been saved off and included in the repo. There are two versions, and models were built on both. The second cleaning data are more suited to the problem and addressed some cleaning/encoding errors.

The modeling notebook takes ~15 minutes to complete. A gradient boosting classifier was the best performer against logistic regression and random forest. Downsampling was used on the negative class to increase recall, sacrificing precision.

Feel free to clone this repo and investigate further. The notebooks should be hosted in a viewable, executeable shape. If there are runtime errors or display issues, please contact me for remediation.
