# Elo Merchant Category Recommendation
'Elo, one of the largest payment brands in Brazil, has built partnerships with merchants in order to offer promotions or discounts to cardholders.' 

1. Timeline
2019.01.05: feature engineering: dt distr, forum, 
2019.01.12: model build
2019.02.19: first due

2. File descriptions
train.csv - the training set
test.csv - the test set
sample_submission.csv - a sample submission file in the correct format - contains all card_ids.
historical_transactions.csv - up to 3 months' worth of historical transactions for each card_id
merchants.csv - additional information about all merchants / merchant_ids in the dataset.
new_merchant_transactions.csv - two months' worth of data for each card_id containing ALL purchases that card_id made at merchant_ids that were not visited in the historical data.


3. Feature engineering --- data mining
Data type: Datetime, Id, Categorical/Ordinal, Numeric
Prepocess: standard scaled
Decision tree based Prepocessing: GBDT(XGBoost), Random Forest, AdaBoosting
Libraries: XGBoost, lightGBM, scikit-learn


# EDA: exploratory data analysis
visualizations: leaks

+ train: <br/>
  - Violineplots: Violin plots are similar to box plots, except that they also show the probability density of the data at different values <br/>
  - target<br/>
  - feature engineering<br/>
+ new_merchant_transactions

########################################################################
pro,con analysis<br/>
feasible <br/>

2019.01.12
correlation analysis: purchase_amount, authorized_flag<br/>
need to more analyze: categories<br/>
outlier analysis: numerical_1<br/>
https://arxiv.org/pdf/1606.07792.pdf<br/>
########################################################################

# Base Model 1:<br/>
+ EDA <br/>
  - df['elapsed_time']
  - gc.collect()

+ feature engineering <br/>
using historical_transactions, new_merchant_transactions<br/>
  - pd.get_dummies(historical_transactions, columns=['category_2', 'category_3'])
  - reduce_mem_usage
  - authorized_flag: authorized_transactions, historical_transactions -= authorized_transactions, auth_mean
  - purchase_month: aggregate_transactions
  - purchase_amount: 
  - ###################
  - history.groupby(['card_id']).agg(agg_func)
  - (history.groupby('card_id').size().reset_index(name='transactions_count'))
  - history.groupby(['card_id', 'month_lag']), groupby('card_id').agg(['mean', 'std'])
  - ###################
  - train merge history, authorized, new, final_group, auth_mean
  - divide features into Categorical and Numeric
  
+ lightGBM  
+ LightGBM-1 with Repeated kfold approach

########################################################################

