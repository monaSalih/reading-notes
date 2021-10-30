# Machine Learning
##  Data Science


Machine learning is the practice of teaching computers how to learn patterns from data, often for making decisions or predictions.

![](https://elitedatascience.com/wp-content/uploads/2018/05/What-Goes-Into-a-Successful-Model.jpg)

## What makes machine learning so special?
### Chapter 1: Bird's Eye View
![](https://elitedatascience.com/wp-content/uploads/2018/05/birds-eye-view.png)
For true machine learning, the computer must be able to learn patterns that it's not explicitly programmed to identify

### Example: the curious child
young child sees and touch candle and burn him and he learn "red and bright thing" will hurt him 

![](https://elitedatascience.com/wp-content/uploads/2017/06/ooh-a-candle.png)

so next time when he see for example stove-top he will remember "red and bright thing" means pain

![](https://elitedatascience.com/wp-content/uploads/2017/06/nope-to-stovetop.png)

### Chapter 2: Exploratory Analysis
![](https://elitedatascience.com/wp-content/uploads/2018/05/exploratory-analysis.png)


#### Why explore your dataset upfront?
exploratory analysis for machine learning should be:
* quick
* efficient
* decisive.
The purpose of exploratory analysis is to "get to know" the dataset. Doing so upfront will make the rest of the project much smoother, in 3 main ways:


1. You’ll gain valuable hints for Data Cleaning (which can make or break your models).


2. You’ll think of ideas for Feature Engineering (which can take your models from good to great).

3. You’ll get a "feel" for the dataset, which will help you communicate results and deliver greater impact.

### Chapter 3: Data Cleaning
![](https://elitedatascience.com/wp-content/uploads/2018/05/data-cleaning.png)

Data cleaning is one those things that everyone does but no one really talks about. 
proper data cleaning can make or break your project. Professional data scientists usually spend a very large portion of their time on this step.

### Better Data > Fancier Algorithms

If you have a properly cleaned dataset, even simple algorithms can learn impressive insights from the data!

> pov: different types of data will require different types of cleaning

### Chapter 4: Feature Engineering
![](https://elitedatascience.com/wp-content/uploads/2018/05/feature-engineering.png)

### What is Feature Engineering?

Feature engineering: is about creating new input features from your existing ones.

* data cleaning look like process of subtraction  
* feature engineering as a process of addition.

* Feature engineering:

the performance of the model is depending on data preprocessing and data handling.

By using Feature Engineering we improve the performance of the model.such as:
❌ if we build a model without Handling data, we got an accuracy of around 70%.

✔ By applying the Feature engineering on the same model there is a chance to increase the performance from 70% to more.

* Create Interaction Features

If a machine learning model makes a prediction based on two features.
The interaction between two features is the change in the prediction that occurs by varying the features after considering the individual feature effects.

* Combine Sparse Classes

Sparse classes (in categorical features) are those that have very few total observations. 
* There's no formal rule of how many each class needs.

* It also depends on the size of your dataset and the number of other features you have.

* As a rule of thumb, we recommend combining classes until each one has at least ~50 observations.

The following example for real-estate data:
![](https://elitedatascience.com/wp-content/uploads/2017/06/grouping-sparse-classes-before.png)

* Group similar classes. In the chart above, the 'exterior_walls' feature has several classes that are quite similar.
>  group 'Wood Siding', 'Wood Shingle', and 'Wood' into a single class. In fact, let's just label all of them as 'Wood'.
* Next, we can group the remaining sparse classes into a single 'Other' class, even if there's already an 'Other' class
> We'd group 'Concrete Block', 'Stucco', 'Masonry', 'Other', and 'Asbestos shingle' into just 'Other'.
![](https://elitedatascience.com/wp-content/uploads/2017/06/grouping-sparse-classes-after.png)

* Add Dummy Variables
Dummy variables use to solve machine learning algorithms problem to handling directly categorical features.

Dummy variables: are a set of binary (0 or 1) variables that each represent a single class from a categorical feature.

In the following example, after grouping sparse classes, we were left with 8 classes, which translate to 8 dummy variables:

![](https://elitedatascience.com/wp-content/uploads/2017/06/Dummy-Variables-Example.jpg)


* Remove Unused Features

>remove unused or redundant features from the dataset.
> Unused features are those that don’t make sense to pass into our machine learning algorithms.

Unused features example:
* ID columns
* Features that wouldn't be available at the time of prediction
* Other text descriptions

### Algorithm Selection

![](https://elitedatascience.com/wp-content/uploads/2018/05/algorithm-selection.png)

#### 5 very effective machine learning algorithms for regression tasks.

1. Why Linear Regression is Flawed:

linear regression models fit a "straight line" (technically a hyperplane depending on the number of features, but it's the same idea).In practice, they rarely perform well. 

simple linear regression suffers from two major flaws:
1. It's prone to overfit with many input features.

2. It cannot easily express non-linear relationships.


![](https://elitedatascience.com/wp-content/uploads/2017/02/noisy-sine-linear-regression.png)


2. Regularization in Machine Learning
Regularization is a technique used to prevent overfitting by artificially penalizing model coefficients.

* It can discourage large coefficients (by dampening them).

*  It can also remove features entirely (by setting their coefficients to 0).

* The "strength" of the penalty is tunable. (More on this tomorrow...)

3. Regularized Regression Algos

* Lasso Regression:stands for Least Absolute Shrinkage and Selection Operator.

* Lasso regression penalizes the absolute size of coefficients.

1. Practically, this leads to coefficients that can be exactly 0.

2. Thus, Lasso offers automatic feature selection because it can completely remove some features.

3. Remember, the "strength" of the penalty should be tuned.

4. A stronger penalty leads to more coefficients pushed to zero.

* Ridge Regression:
1. Ridge regression penalizes the squared size of coefficients.

2. Practically, this leads to smaller coefficients, but it doesn't force them to 0.

3. In other words, Ridge offers feature shrinkage.

4. The "strength" of the penalty should be tuned.

5. A stronger penalty leads to coefficients pushed closer to zero.

* Elastic-Net:is a compromise between Lasso and Ridge.

1. Elastic-Net penalizes a mix of both absolute and squared size.

2. The ratio of the two penalty types should be tuned.

3. The overall strength should also be tuned.

4. Decision Tree Algos:
Decision trees model data as a "tree" of hierarchical branches. They make branches until they reach "leaves" that represent predictions.
![](https://elitedatascience.com/wp-content/uploads/2017/06/Decision-Tree-Example.jpg)

> branching structure, decision trees can easily model nonlinear relationships.

5. Tree Ensembles
Ensembles are machine learning methods for combining predictions from multiple separate models.

* Bagging
Bagging attempts to reduce the chance overfitting complex models.

1. It trains a large number of "strong" learners in parallel.

2. A strong learner is a model that's relatively unconstrained.

3. Bagging then combines all the strong learners together in order to "smooth out" their predictions.

* Boosting
Boosting attempts to improve the predictive flexibility of simple models.

1. It trains a large number of "weak" learners in sequence.

2. A weak learner is a constrained model (i.e. you could limit the max depth of each decision tree).

3. Each one in the sequence focuses on learning from the mistakes of the one before it.

4. Boosting then combines all the weak learners into a single strong learner.

when the base models are decision trees, they have special names: random forests and boosted trees!

* Random forests:


![](https://elitedatascience.com/wp-content/uploads/2017/06/Random-Forest-Color-Icon.png)

* Boosted trees
![](https://elitedatascience.com/wp-content/uploads/2017/06/Boosted-Tree-Color-Icon.png)


### Model Training

Model training is the phase in the data science development lifecycle where practitioners try to fit the best combination of weights and bias to a machine learning algorithm to minimize a loss function over the prediction range.

Why is it Important?
Model t raining is the key step in machine learning that results in a model ready to be validated, tested, and deployed.