# Housing Price Predictions With Linear Regression

#### Project by: Bruno Santos

### Contents

- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Data](#Data)
- [Conclusion and Recommendations](#Conclusion-and-Recommendations)

## Problem Statement

We are tasked with creating a regression model based on the Ames Housing Dataset. This model will predict the price of a house at sale.

We will explore our data, clean it, and inspect how different variables affect residential sale prices in Ames, Iowa. Do certain variables have a greater impact on overall sales prices, and if so what are those variables? How can we use these variables to accurately predict what a property's sales price will be?

## Executive Summary

The Ames Housing Dataset is an exceptionally detailed and robust dataset with over 70 columns of different features relating to houses. The dataset contains information from the Ames Assessor’s Office used in computing assessed values for individual residential properties sold in Ames, IA from 2006 to 2010.

The goal is to use the data contained within the Ames Housing Dataset to predict housing prices as accurately as possible. We will be utilizing the existing columns of features within the dataset, feature engineering to create new columns as necessary, removing data as we deem appropriate, and building and refining multiple different linear regression models to find the model that we feel most accurately predicts residential real estate prices.

In addition to exploring, cleaning, and visualizing data, we will be using our models to submit predictions on Kaggle - an online community of data scientists and machine learners, owned by Google.

## Data

Our data, including descriptions on features and what they mean, can be found [here](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt)

## Conclusion and Recommendations

In conclusion, we can see that while the Ames Housing Dataset has a large number of columns, certain columns are significantly more impactful when predicting housing prices - such as square footage, quality (both overall and of select features), and - most importantly - the neighborhood (or location). Some features negatively impact the overall price of a home, such as the age of the home. Many of the features that have an impact on the home's price are those that can be renovated (or improved) to increase their 'quality metric', such as overall quality, exterior quality, and kitchen quality.

While there are certain metrics that can be improved, the most important metric is without a doubt the location of the home. Where a home is located is fixed and cannot be changed - and in many cases surrounding homes and the surrounding area in general will have the greatest impact. Another metric that cannot be changed is the lot area, and in some cases the overall square footage of a home (as this will depend on each jurisdiction's allowance of building square footage to lot area ratio).

It's possible that this model will generalize well to other cities, however it would have to be fine-tuned to take the overall values of homes and neighborhoods into consideration. For example, housing prices in Ames, Iowa will vary greatly from housing prices in Manhattan, Los Angeles, or Washington, DC - as will available houses and the weight of certain features. If we had similar data to what is available in the Ames Housing Dataset for other cities, we could use our model to learn the overall weights of specific features and apply that to more accurately predict housing prices.

TECHNICAL SUMMARY

In terms of model performance, my Ridge Regression with built-in cross validation (RidgeCV) model performed the best, both in terms of lowest RMSE (roughly 0.11 RMSE) and closest R2 Score between the training data (92.97% accuracy) and the testing data (92.31% accuracy). To build this model, I scaled all of my independent variables (features) and used the log of my dependent variable (sale price) to train the model. When it came time to predict on the never-been-seen Test dataset, my model predicted the exponentiation of the saleprice to account for learning on log variables.

The second-best performing model was my Lasso Regression with built-in cross validation (LassoCV) model. This model had a higher RMSE at roughly 691.83, and the R2 Scores were a bit more spread out (93.01% accuracy on training data, 91.53% accuracy on testing data). Similar to the RidgeCV model above, this model was built with scaled independent variables and with the log of the saleprice as the dependent variable. The Lasso model zeroed out 53.78% of the independent variable coefficients passed through the model.