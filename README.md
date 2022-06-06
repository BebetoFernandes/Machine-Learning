# Machine Learning

Repo created with the goal to store and share useful (I hope so rsrs) examples of activities present on the Machine Learning/Data Science pipeline. 
Examples include, but not limited to, data collection, preprocessing and modelling. 


## Data Collection
### SQL
We commonly see ourselves in need for reaching our data elsewhere before being able to use it on data wrangling, feature engineering, modelling, dashboards creation and other activities. Structured Query Language **SQL** is the most common programming language when we are dealing with relational database where we can query our data and perform operations on it. In Machine Learning scenarios more diverse options are possible (Spark is one example that we are going to discuss in sequence) but when we talk about data Analytics, SQL is by far the most requested. Below you can find tutorials with SQL great explanations as well as a combination with first lessons of big query commands.
[Repository with SQL Tutorials](https://github.com/BebetoFernandes/SQL---Intro-to-Advanced)

### Spark
Spark is a multi-language engine that can be used for executing data engineering, data science, and machine learning on single-node machines or clusters. It comes to the game when we need to handle data in large scale where other querying and processing options present itself as unproductive options. More detailed explanations are provided in the link below (Portuguese version, please contact me if you have any trouble reading it or need further assistance). Although there are different usage examples of it, I am adding Spark in this step of Data Collection as all my previous experiences with the language were related to high speed data querying, analysis, and transformations before going to the next steps. (OBS: Analysis and machine learning tasks are also possible and may even be discussed here in the future, but for now I am just keeping the example that i am more familiar with)
[Spark Notebook Reference](notebook_final_referencia.ipynb)

## Data Quality


## EDAs (Exploratory Data Analysis)


## Modelling
**1. Loan Default Prediction Based on Phone Recharge Behavior**<br />
It is a complete example (from business needs analysis to Modelling, goinh through EDA and Data Manipulation techniques) which deals with a Telco's problem of recharging loan default. The main idea was to create a model with historical recharging data that could classify if a recharge loan would default or not.<br />
[Delinquency_Classification](https://github.com/BebetoFernandes/Machine-Learning-Models/blob/master/Delinquency_Classification_Classifica%C3%A7%C3%A3o_de_Inadimpl%C3%AAncia.ipynb)


## Model Deployment


## Feature Selection
**1. Damien Benveniste Feature Selection Technique**<br />
This feature selection method is called by Damien as the "Random Bar"! It basically adds a new random feature to a simple modelling process and then compare it to the 'real' features using a feature importance plot. The 'real' features with importance lower or equivalent to the random can be discarded. Full explanation below:

Let's assume you have a feature set X and a target Y. Let's create a random vector V (for example np.random.normal(size=(1, 100))) and append that vector as a new feature to X:

X' = [X, V]

X' is just the original feature set with additionally the new random feature. Keep in mind that this new feature cannot possibly help to predict the target Y since it is random! Now, take that data (X', Y) and train a Supervised Learning algorithm with a Feature Importance measure that is relevant for you application. Intuitively, the mean entropy gain per split of tree based algorithms (Random Forest, Xgboost, ...) is a convincing measure of feature importance. The statistical fluctuation of the data is such that even the random feature will be attributed a non-zero feature importance by the algorithm, but we know it is artificial. Any feature with a lower feature importance than the random feature has to be useless to predict the target and the features with a higher feature importance are at least better than random noise at predicting the target. 

This is especially useful if you have thousands of features and you want to weed out quickly the ones that won't have any impact in the learning process. This is also a method that can be used for highly non-linear data as opposed to LASSO (for example) that tends to only understand linear relationships in the data. The random feature is a "Random Bar" because this is the minimum bar a feature needs to beat to be a part of the potentially useful features set. Now it doesn't mean there are not additional features that could be beneficial to further remove to optimize your model.<br />
![image](https://user-images.githubusercontent.com/55111736/170554154-0d20d49e-4fb2-451e-b727-3072b1492a79.png)


## Data Drift Analysis
