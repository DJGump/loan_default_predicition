# Small Business Loans: Predicting Outcome


##### Contents
* 2 Jupyter notebooks, for data cleaning and modeling
* A PDF slide deck, being the visual synthesis of the project
* A README (You are here. Thank you.)
* Various figure files used in the slides
* A data folder, containing my cleaned data and source documentation.

The original data was taken from Kaggle, and can be found [here](https://www.kaggle.com/mirbektoktogaraev/should-this-loan-be-approved-or-denied?select=SBAnational.csv). This is historical data from the Small Business Administration (SBA), assembled and distributed as a teaching tool for aspiring bankers. For context, the SBA sponsors a program ensuring a portion of a small business loan. A description of the SBA loan program can be found [here](https://www.sba.gov/offices/headquarters/ofa/resources/11421).

### Results and Discussion

By approaching the dataset form the perspective of the SBA, I was able to create and solve new problems, namely by focusing on correctly predicting more of the defaulted loans and at the cost of incorrectly identifying more paid-off loans. The SBA exists to help businesses, so they may want to prioritize insuring loans that would not be granted without their support, even if it is likely that loan will default and result in a payout from the SBA. Likewise, recall was maximized with a gradient boosting classifier, reaching 95%. There is no harm to a business if it is denied support because of an incorrect prediction of default; the loan ends up paid. However, if there are a limited number of commitments to give, too many businesses may receive SBA backing who ended up not needing it. This is evident by the 68% precision score. This means 32% predictions to default were incorrect, and the loan was paid off. If the model proves valid in the wild, these scoring metrics can help accurately determine how many loans can be commited to without going over budget. An outstanding question is how the SBA decides to back loans based on likelihood of default.

The most important feature to prediction was if a business was approved for a Low Document application. This and the loan amount are kinds of prescreening indicators of how a business might perform. The bank state was the next most important feature. This could be made more useful for by tying industry proportions to the states or considering specific years for specific states. There is a relationship with bank size and loan amount, with bigger banks giving smaller loans for shorter time periods. A big bank is likely able to take on more risk and afford defaulting loans. There may even be money to be made in defaulted loans in the long run. These could be factores considered when making manual decisions about where to put SBA money. Engineering new features and introducing new data is always will be the best way to improve performance and gain insight.

Rigorous validation would be on the scale of years. A true A/B trial for upwards of ten years would be needed, with close collaboration of the business team to ensure targets are measured accurately. In the mean time, this model could serve as the nucleus for a software tool supplementing human decisions. It could even be tuned to favor different errors. Regardless, don't expect this to level the field. Being built on historical data means historical trends are represented. Fostering diversity and inclusion is in line with the SBA's mission, and external information will be needed to ensure equity of underrepresented populations to the specifications of the SBA. This could be a great source of new data while supporting a developing market.



### Notes About the Code
The data cleaning notebook does not need to be executed to run the models. The cleaned data have been saved off and included in the repo. There are two versions, and models were built on both. The second cleaning data are more suited to the problem and addressed some cleaning/encoding errors.

The modeling notebook takes ~15 minutes to complete. A gradient boosting classifier was the best performer against logistic regression and random forest. Downsampling was used on the negative class to increase recall, sacrificing precision.

Feel free to clone this repo and investigate further. The notebooks should be hosted in a viewable, executeable shape. If there are runtime errors or display issues, please contact me for remediation.
