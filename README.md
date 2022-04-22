# House Price Prediction for Ames, Iowa


## Problem Statement
As an employee at a real estate company, that specializes in buying houses, renovating them if need be and selling them, I have been tasked to study the housing data, determine important features that sell the house and develop an algorithm that will predict the price of a house, using these features, for the company to make profit.  


## Summary
The data used for project is from [Kaggle](https://www.kaggle.com/c/dsir-0124-project-2-regression-challenge/data), and consists of data of 2051 homes in the train dataset and 878 homes in the test dataset. There are 81 features in the train data, and 80 in test data with the Sale Price excluded.

The goal is to identify the important features and build a model using the training data and test the model on testing data by predicting the Sale Price and submitting it on Kaggle. The Root Mean Square Error (RMSE), is the metric obtained after submitting Sale Price predictions on Kaggle. The goal is to minimize this error and predict the price closest to the actual sale price.

Following are the steps involved for achieving the goal:
1. Data Gathering - Gathering the data and understanding what different columns mean.
2. Data Cleaning/Munging - Checking the integrity of the data. Checking for missing values & imputing missing values.
3. Exploratory Data Analysis - Checking for unusual values in the data, analyzing them and correcting them if need be. Checking data distributions and correlations.
4. Modeling - After analyzing and determining the important features, building a model that best describes the data. Splitting the known data into train and test datasets and training the model on train data to evaluate the its performance by predicting and comparing it with test data. Based on the evaluation, tuning the model. If needed, re-evaluating step 3 to improve the model by improving features.
5. Reporting - Once the model satisfies evaluation metrics, using the model on unseen data to predict target variable, and conveying findings.

After cleaning the data, understanding the correlation within different columns and with Sale Price, features that affect Sale Price of the house were determined. Amongst these features were numerical features and ordinal & nominal features that were turned into numerical features either using one hot encoding, or using exploratory data analysis.

All these features were used to overfit the model, and regularize the model using the Lasso Regression. Based on results from initial lasso regression, features were selected and using these features, an improved lasso model was built and compared to linear regression and ridge regression models. All the model evaluations were performed on train data, by splitting the data into train & test datasets and testing the model performance based on R2 scores and cross_val_scores. Amongst all the models, Lasso Regression model surfaced as the best fitting model for the data. The model exhibited .85 cross_val_score which means 85% of variance in the Sale Price can be explained by the model. The model's performance was better than the Baseline model.


## Conclusion

Based on the model predictions, both structural and internal factors contribute to the Sale Price of the house. Overall Quality i.e. overall material and finish of the house has the highest positive impact on the price, followed by Total Living Area in sq. ft. of the house. These are followed by Garage Cars, which is essentially the garage space, and Overall Condition of the house. Remodeling a house brings up the price. Internal factors like number of baths, bedrooms, basement sq. ft. area have a strong positive effect on Sale Price. Finished Basement also has a positive effect but not as much as having a bigger basement. Having a fireplace certainly brings up the Sale Price of the house. External factors that help increase the price of the house are Paved Driveway, Screen Porch, Wooden Deck and an Enclosed Porch.

A strong deterring factor, and also an obvious one, to the Sale Price is Age of the house. Value of Miscellaneous Features of the House are also a deterring factor to Sale Price. Pool area is a negative factor for Sale Price. This maybe because of the time and resources involved in maintaining it. An excellent kitchen is not so much a positive factor on the Sale Price as a typical/average quality is a negative factor. Gravel Street is not a positive choice. When it comes to Electrical Systems of the House, most of the old houses have Mixed wiring, i.e. a mix of both old and new wires in the system. This also contributes negatively towards the price of the house.


## Recommendations

The model built to predict Sale Price still has room for improvement. More features and their correlation can be studied, and additional feature engineering can be included in the model. Missing data has been imputed using mean, median or mode which are the basic ways of imputing data. Linear regression model can be used to understand and predict missing data.

Overall Condition and Overall Quality of the house are strong positive factors for Sale Price. Inspite of having a metric 1-10, they are vague. It would be worth looking into these metrics and identifying factors that contribute to bring these metrics up.

A way of increasing Sale Price on an old house is Remodeling. With more information on remodeling time and cost required, a better prediction can be made on how to reduce price loss on old homes.
