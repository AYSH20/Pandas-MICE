# Pandas-MICE

This project provides an Sklearn type interface for imputing independent variables using MICE (Multiple Imputation by Chained Equations). MICE has become an industry standard way of dealing with null values while preprocessing data. It is argued that by simply using fill values such as the mean or mode we are throwing information away that is present in other variables that might give insight into what the null values might be. With that thought in mind, we predict the null values from the other features present in the data. Thus preserving as much information as possible. If the data is not missing at random (MAR) then this method is inappropriate. Instead use a feature descritization method.

## Features:
* The model preserves the users pandas dataframe column and row indexes. 
* The model can be fit on past data and applied to new unseen data using fit and transform methods separate from one another. This allows for supporting machine learning applications.
* Only columns that are never null in the training set are used to fit the model unless the user sets the "seed_nulls" argument to "True". This then fills all other nulls in the data based on the standard Sklearn Imputer methods. The null target variable is then predicted using this filled data.
* A class variable holds the fitted models for each feature in a dictionary that can be accessed through the API. This can be saved and used at a later time if needed.

A future improvement to this project would be to add a function that allows the user to change the method used for estimating the missing values. Such as applying k-nn or random forest instead of linear models.


