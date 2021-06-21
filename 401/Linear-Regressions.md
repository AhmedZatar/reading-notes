# How to run Linear regression in Python scikit-Learn
You know that linear regression is a popular technique and you might as well seen the mathematical equation of linear regression. But do you know how to implement a linear regression in Python?? If so don’t read this post because this post is all about implementing linear regression in Python. There are several ways in which you can do that, you can do linear regression using numpy, scipy, stats model and sckit learn. But in this post I am going to use scikit learn to perform linear regression.

![0](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Prices.png)

Scikit-learn is a powerful Python module for machine learning. It contains function for regression, classification, clustering, model selection and dimensionality reduction. Today, I will explore the sklearn.linear_model module which contains “methods intended for regression in which the target value is expected to be a linear combination of the input variables”.

In this post, I will use Boston Housing data set, the data set contains information about the housing values in suburbs of Boston. This dataset was originally taken from the StatLib library which is maintained at Carnegie Mellon University and is now available on the UCI Machine Learning Repository. UCI machine learning repository contains many interesting data sets, I encourage you to go through it.

Exploring Boston Housing Data Set

The first step is to import the required Python libraries into Ipython Notebook.

![1](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Explore-1.png)

This data set is available in sklearn Python module, so I will access it using scikitlearn. I am going to import Boston data set into Ipython notebook and store it in a variable called boston.

![2](https://bigdata-madesimple.com/wp-content/uploads/2016/04/sklearn.png)

The object boston is a dictionary, so you can explore the keys of this dictionary.

![3](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-keys.png)

![4](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-data-shape1.png)

I am going to print the feature names of boston data set.

![5](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-features.png)

I will see the description of this data set to know more about it. In this data set I have 506 instances(rows) and 13 attributes or parameters(columns). The goal of this exercise is to predict the housing prices in boston region using the features given.

![6](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-description.png)

![7](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Attribution.png)

I am going to convert boston.data into a pandas data frame.

![8](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Pandas-DataFrame.png)

As you can see the column names are just numbers, so I am going to replace those numbers with the feature names.

![9](https://bigdata-madesimple.com/wp-content/uploads/2016/04/bos-columns.png)

boston.target contains the housing prices.

![10](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Boston-target.png)

I am going to add these target prices to the bos data frame.

![11](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Bos-Price.png)

![12](https://bigdata-madesimple.com/wp-content/uploads/2016/04/RAD.png)

## Scikit Learn
In this section I am going to fit a linear regression model and predict the Boston housing prices. I will use the least squares method as the way to estimate the coefficients.

Y = boston housing price(also called “target” data in Python)

and

X = all the other features (or independent variables)

First, I am going to import linear regression from sci-kit learn module. Then I am going to drop the price column as I want only the parameters as my X values. I am going to store linear regression object in a variable called lm.

![13](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Skitlearn-linear-model1.png)

If you want to look inside the linear regression object, you can do so by typing LinearRegression. and the press < tab > key. This will give a list of functions available inside linear regression object.

![14](https://bigdata-madesimple.com/wp-content/uploads/2016/04/linear-regression.png)

Important functions to keep in mind while fitting a linear regression model are:

lm.fit() -> fits a linear model

lm.predict() -> Predict Y using the linear model with estimated coefficients

lm.score() -> Returns the coefficient of determination (R^2). A measure of how well observed outcomes are replicated by the model, as the proportion of total variation of outcomes explained by the model.

You can also explore the functions inside lm object by pressing lm.<tab>

![15](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Lm.png)

.coef_ gives the coefficients and .intercept_ gives the estimated intercepts.

![16](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Output.png)

## Fitting a Linear Model

I am going to use all 13 parameters to fit a linear regression model. Two other parameters that you can pass to linear regression object are fit_intercept and normalize.

In [ 20 ]: lm.fit(X, bos.PRICE)

Out[ 20 ]: LinearRegression(copy_X=True, fit_intercept=True, normalize=False)

I am going to print the intercept and number of coefficients.

![17](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Estimated-Coeff.png)

I then construct a data frame that contains features and estimated coefficients.

![18](https://bigdata-madesimple.com/wp-content/uploads/2016/04/pd-data-frame.png)

As you can see from the data frame that there is a high correlation between RM and prices. Lets plot a scatter plot between True housing prices and True RM.

![19](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Scatter-plot.png)

![20](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Relationship-between-RM-and-Price.png)

As you can see that there is a positive correlation between RM and housing prices.

## Predicting Prices
I am going to calculate the predicted prices (Y^i) using lm.predict. Then I display the first 5 housing prices. These are my predicted housing prices.

![21](https://bigdata-madesimple.com/wp-content/uploads/2016/04/lm-predict.png)

Then I plot a scatter plot to compare true prices and the predicted prices.

![22](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Scatter-plot-in-the-pandas.png)

![23](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Prices-vs-predicted-prices.png)

You can notice that there is some error in the prediction as the housing prices increase.

## Residual Plots

Residual plots are a good way to visualize the errors in your data. If you have done a good job then your data should be randomly scattered around line zero. If you see structure in your data, that means your model is not capturing some thing. Maye be there is a interaction between 2 variables that you are not considering, or may be you are measuring time dependent data. If you get some structure in your data, you should go back to your model and check whether you are doing a good job with your parameters.

![24](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Plt-scatter.png)

![25](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Residual-plot.png)

