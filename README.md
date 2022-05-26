# Machine Learning

Repo created with the goal to store and share useful (I hope so rsrs) examples of activities present on the Machine Learning/Data Science pipeline. 
Examples include, but not limited to, data collection, preprocessing and modelling. 

## Models
**1. Loan Default Prediction Based on Phone Recharge Behavior**
It is a complete example (from business needs analysis to Modelling, goinh through EDA and Data Manipulation techniques) which deals with a Telco's problem of recharging loan default. The main idea was to create a model with historical recharging data that could classify if a recharge loan would default or not. 
https://github.com/BebetoFernandes/Machine-Learning-Models/blob/master/Delinquency_Classification_Classifica%C3%A7%C3%A3o_de_Inadimpl%C3%AAncia.ipynb

## EDAs (Exploratory Data Analysis)

## Data Collection

## Feature Selection
**1. Damien Benveniste Feature Selection Technique**

This feature selection method is called by Damien as the "Random Bar"! It basically adds a new random feature to a simple modelling process and then compare it to the 'real' features using a feature importance plot. The 'real' features with importance lower or equivalent to the random can be discarded. Full explanation below:

Let's assume you have a feature set X and a target Y. Let's create a random vector V (for example np.random.normal(size=(1, 100))) and append that vector as a new feature to X:

X' = [X, V]

X' is just the original feature set with additionally the new random feature. Keep in mind that this new feature cannot possibly help to predict the target Y since it is random! Now, take that data (X', Y) and train a Supervised Learning algorithm with a Feature Importance measure that is relevant for you application. Intuitively, the mean entropy gain per split of tree based algorithms (Random Forest, Xgboost, ...) is a convincing measure of feature importance. The statistical fluctuation of the data is such that even the random feature will be attributed a non-zero feature importance by the algorithm, but we know it is artificial. Any feature with a lower feature importance than the random feature has to be useless to predict the target and the features with a higher feature importance are at least better than random noise at predicting the target. 

This is especially useful if you have thousands of features and you want to weed out quickly the ones that won't have any impact in the learning process. This is also a method that can be used for highly non-linear data as opposed to LASSO (for example) that tends to only understand linear relationships in the data. The random feature is a "Random Bar" because this is the minimum bar a feature needs to beat to be a part of the potentially useful features set. Now it doesn't mean there are not additional features that could be beneficial to further remove to optimize your model.

![image](https://user-images.githubusercontent.com/55111736/170554154-0d20d49e-4fb2-451e-b727-3072b1492a79.png)


## Data Drift Analysis
