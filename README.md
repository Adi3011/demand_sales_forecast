# DEMAND SALES FORECAST
--> I have taken this dataset from a kaggle competition. This dataset comes under the category of demand forecasting.
--> The dataset contains more than 900000 rows and 4 features.
--> The important thing in this dataset is that as features are less and the only feature from which we can get some information 
    is the main target variable which is sales.
    
# EXPLORATORY DATA ANALYSIS    

Firstly i did EDA on this data and created some new features out of the date like day,month,year,weekday and weekday name
I tried to found out that how sales changed with months ,years and weekdays.
I found that the sales were good on friday ,saturday and sunday
Also the data was little skewed so i took used logarathmic transformation to avoid skewness.
The dataset contains outlier too which could be easily found using boxplot.
The outliers were removed by using the five number summary .

# FEATURE ENGINEERING 
I this i created some lag/shift features from target variable which is sales.
lag1 means the amount of 1 day before sale for each sale.
Also this lag feature was created in such a way so that their is gap of 90 days for the first lag.
As in the test we are hoping to get sales for the first three months.
After creating this feature,their were some null values which were replaced by mean in their respective columns.

# FEATURE SELECTION AND MODEL
 I used different models and compared them on the basis of smape which symmetric mean average percentage error. The lesser the
 smape the more better the model is.
  After doing the train test split on the training data available i tried different models.
  1) linear regression
  2) lasso regression
  3) ridge 
  4) polynomial regression
  5) random forest regressor
  6) lgm
Out of these polynomial regression showed better performance with smape as 4.5 approx.
But as we were given the testing data separately in which we have to predict sales for next 3 months.
And also all the newly added features while training will contain nan value definetly in the testing file so
I used light gbm as the alternative to generate sales.
my smape score for testing data given was 14 approx which can be improved a little more if we create some well defined features from sales.
==> now polynomial regression was not used on testing file because because it contained nan values which maybe we cant replace . 


