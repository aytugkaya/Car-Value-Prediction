ABSTRACT:

Motive:
Each day, thousands of pre-owned cars are sold worldwide. Prediction of the second-hand vehicle price provides an important benchmark to both private buyer and the seller as well as business professionals such as car dealers, lenders and insurance companies.

Dataset:
The dataset used for this project was retrieved from Kaggle.com. The original dataset is a German used car sales website and each data point is an advertisement placed by an individual. The dataset is therefore quite arbitrary, with great percentage of missing data, most of which cannot be completed with interpolation or other conventional fill methods.

A multi stage filtering was introduced to remove erroneous data. After that, case specific code was written in order to be able to retrevie data that was found in title of the advertisement, which then in return was used to fill missing values of brands / models.

Once all erroneous data points and non-fillable missing values have been deleted, approximately 232 thousand data points out of 377 thousand data points remained, which is 62% of the original data. Data fidelity was preferred over the number of data points remaining, since data precision heavily affects model quality.

ML Models:
In order to better model this diverse dataset, initially, DecisionTreeRegressor, RandomForestRegressor, BaggingRegressor, GradientBoost, Adaboost and Ridge were evaluated.

• Dummy variables were created so that categorical features could be inserted to the model.
• Data was split to various test fractions from %20 to %40 by train test split.
• Model was instantiated and then fit on training data.
• Cross-validation of 3-10 folds were applied, depending on processing time.
• Fitted model predicted test set values, the unseen part of the dataset.
• Grid-search and Randomized search and hyper parameter tuning was carried out, processing power and time permitting.
• Sklearn metrics R2 and RMSE were used for scoring.

In order to reduce the RMSE, the price column (labels) of the dataset was transformed to logarithmic scale and the prediction models were re-run together with the introduction of LightGBM(LGB) and CatBoostRegressor(CB). Moreover, the last stage of the data filtering were reverted, including very old and very expensive cars, increasing the spread of the data. 

After the log or box-cox transformation, RMSE results as low as 1.40$ were acheieved.

Conclusion:
An arbitrary database retrieved from German online sale website has been retrieved from Kaggle.com. After an extensive data cleaning and manipulation process, data frame was price column has been predicted by numerous non-linear machine learning models. Following normalization via log or box cox transformation, all models were able to predict with root mean square error of less than 2€, with the best regressor error being as low as 1.40€. Error rates are interpreted to be compatible with market demand explained in the “Problem Statement”



! IMPORTANT !

Please observe documentation / stage documentation for details.

For data wrangling and EDA phase use Final version_9 file. To start with clean data and observe machine learning phase open machine learning file.


 Data file "autos.csv" and "clean_data" could not be uploaded since file is too large. 
 Please download zipped files or use the link to download "autos.csv" data file.

