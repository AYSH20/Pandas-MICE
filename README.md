# Pandas-MICE

This project provides an Sklearn type interface for imputing independent variables using MICE. The user can seed all other nulls except the target column using the standard Sklearn Imputer method by setting the seed_nulls flag to True. Otherwise the model searches for variables that are never null and uses those as features to predict the null target.

This model preserves the users pandas dataframe column and row indexes. The model can be fit on past data and applied to new unseen data using fit and transform methods separate. In the spirit of Sklearn, the fit_transform method chains together the two methods.

A future improvement to this project could be adding a function change the predictive model used to estimate the missing values. Such as applying k-nn or random forest instead of linear models.
