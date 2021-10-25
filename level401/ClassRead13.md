# How to run Linear regression in Python scikit-Learn

![tes](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Prices.png)

## Regression searches for relationships among variables.


### 🎉🎉🎉lets have fun with linear regression🎉🎉🎉
* Exploring Boston Housing Data Set
The first step is to import the required Python libraries into Ipython Notebook.

![cn](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Explore-1.png)

I am going to import Boston data set into Ipython notebook and store it in a variable called boston.

![ew](https://bigdata-madesimple.com/wp-content/uploads/2016/04/sklearn.png)

The object boston is a dictionary, so you can explore the keys of this dictionary.

![ad](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-keys.png)

The goal of this exercise is to predict the housing prices in boston region using the features given.

![ad](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-description.png)

I am going to convert boston.data into a pandas data frame.

![jds](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Pandas-DataFrame.png)

we can replace numbers to feature names

![jds](https://bigdata-madesimple.com/wp-content/uploads/2016/04/bos-columns.png)

___________________________________________________________
__Scikit-learn__ is a powerful Python module for machine learning. It contains function for regression, classification, clustering, model selection and dimensionality reduction. Today, I will explore the sklearn.
There are five basic steps when you’re implementing linear regression:

1. Import the packages and classes you need.
The first step is to import the package numpy and the class LinearRegression from sklearn.linear_model:
```
import numpy as np
from sklearn.linear_model import LinearRegression
```

2. Provide data to work with and eventually do appropriate transformations.
The second step is defining data to work with. The inputs (regressors, 𝑥) and output (predictor, 𝑦) should be arrays (the instances of the class numpy.ndarray) or similar objects. This is the simplest way of providing data for regression:
```
x = np.array([5, 15, 25, 35, 45, 55]).reshape((-1, 1))
y = np.array([5, 20, 14, 32, 22, 38])
```
3. Create a regression model and fit it with existing data.
The next step is to create a linear regression model and fit it using the existing data.
```
model = LinearRegression()
```
You can provide several optional parameters to LinearRegression:

* fit_intercept is a Boolean (True by default) that decides whether to calculate the intercept 𝑏₀ (True) or consider it equal to zero (False).

* normalize is a Boolean (False by default) that decides whether to normalize the input variables (True) or not (False).

* copy_X is a Boolean (True by default) that decides whether to copy (True) or overwrite the input variables (False).

* n_jobs is an integer or None (default) and represents the number of jobs used in parallel computation.

3. Check the results of model fitting to know whether the model is satisfactory.
Once you have your model fitted, you can get the results to check whether the model works satisfactorily and interpret it.

You can obtain the coefficient of determination (𝑅²) with .score() called on model:
```
>>> r_sq = model.score(x, y)
>>> print('coefficient of determination:', r_sq)
coefficient of determination: 0.715875613747954
```

4. Apply the model for predictions.

Once there is a satisfactory model, you can use it for predictions with either existing or new data.

To obtain the predicted response, use .predict():
```
>>> y_pred = model.predict(x)
>>> print('predicted response:', y_pred, sep='\n')
predicted response:
[ 8.33333333 13.73333333 19.13333333 24.53333333 29.93333333 35.33333333]
```

## Fitting a Linear Model
Two other parameters that you can pass to linear regression object are fit_intercept and normalize.
![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Estimated-Coeff.png)

then construct a data frame that contains features and estimated coefficients.
![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/pd-data-frame.png)

## How to do train-test split:
dividem data sets randomly. Scikit learn provides a function called train_test_split to do this.

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Xtrain-and-Xtest.png)
