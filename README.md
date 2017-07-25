# Pandas-MICE

This project provides an Sklearn type interface for imputing independent variables using MICE (Multiple Imputation by Chained Equations). The user can seed all other nulls except the null target feature using the standard Sklearn Imputer method by setting the seed_nulls flag to True. Otherwise the model searches for variables that are never null and uses those as features to predict the null target.

This model preserves the users pandas dataframe column and row indexes. The model can also be fit on past data and applied to new unseen data using fit and transform methods separate from one another. In the spirit of Sklearn, the fit_transform method chains together the two methods.

A future improvement to this project would be to add a function that allows the user to change the method used for estimating the missing values. Such as applying k-nn or random forest instead of linear models.

Multiple imputation has become an industry standard way of dealing with null values while preprocessing data. It is argued that by simply using fill values such as the mean or mode we are throwing information away that is present in other variables that might give insight into what the null values might be. With that thought in mind, we predict the null values from the other features present in the data. Thus preserving as much information as possible.
