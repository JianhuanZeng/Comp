# Elo Merchant Category Recommendation
'Elo, one of the largest payment brands in Brazil, has built partnerships with merchants in order to offer promotions or discounts to cardholders.' 

## Timeline
2019.01.05: feature engineering: dt distr, forum, 
2019.01.12: model build
2019.02.19: first due

## File descriptions
train.csv - the training set
test.csv - the test set
sample_submission.csv - a sample submission file in the correct format - contains all card_ids.
historical_transactions.csv - up to 3 months' worth of historical transactions for each card_id
merchants.csv - additional information about all merchants / merchant_ids in the dataset.
new_merchant_transactions.csv - two months' worth of data for each card_id containing ALL purchases that card_id made at merchant_ids that were not visited in the historical data.


### feature engineering --- data mining
Data type: Datetime, Id, Categorical/Ordinal, Numeric
Prepocess: standard scaled
Decision tree based Prepocessing: GBDT(XGBoost), Random Forest, AdaBoosting
Libraries: XGBoost, lightGBM, scikit-learn

########################################################################
### exploratory data analysis
- visualizations: leaks

+ train: 
- Violineplots: Violin plots are similar to box plots, except that they also show the probability density of the data at different values 
- target
- feature engineering

+ new_merchant_transactions



########################################################################
pro,con analysis
feasible 

########################################################################
2019.01.12
correlation analysis: purchase_amount, authorized_flag
need to more analyze: categories
outlier analysis: numerical_1
