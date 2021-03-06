# Insurance Claim - Fraud Detection with Dataiku DSS
[![Dataiku](https://img.shields.io/static/v1?style=for-the-badge&message=Dataiku&color=2AB1AC&logo=Dataiku&logoColor=FFFFFF&label=)](https://community.dataiku.com/t5/user/viewprofilepage/user-id/7023)
[![Kaggle](https://img.shields.io/static/v1?style=for-the-badge&message=Kaggle&color=222222&logo=Kaggle&logoColor=20BEFF&label=)](https://www.kaggle.com/)
[![GitHub](https://img.shields.io/static/v1?style=for-the-badge&message=GitHub&color=181717&logo=GitHub&logoColor=FFFFFF&label=)](https://github.com/sulaihasubi)

<a href="https://github.com/sulaihasubi/insurance-claims-fraud-detection/commits/master">
        <img alt="Last commit" src="https://img.shields.io/github/last-commit/sulaihasubi/insurance-claims-fraud-detection">
</a>

## :heart: Contributor

<a href="https://github.com/sulaihasubi/insurance-claims-fraud-detection/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=sulaihasubi/insurance-claims-fraud-detection" />
</a>

## ✍🏻 Table of Contents
- [About this Project](#about-this-project)
- [Introduction](#introduction)
- [📖 Problem Statements](#-problem-statements)
- [📊 About the Dataset](#-about-the-dataset)
- [🧮 Algorithm](#-algorithm)
- [🖥 The Flow](#-the-flow)
- [📊 Statistic Card](#-statistic-card)
- [🤖 Create Machine Learning Model (Auto ML) & Analysed the Results - Training Models](#-create-machine-learning-model-auto-ml--analysed-the-results---training-models)


## About this Project
Since Github have limitation of size to support the files upload, you can explore about this project with Dataiku DSS by downloading the file with the link provided as below:
<br/>
<br/>
[![Google Drive](https://img.shields.io/static/v1?style=for-the-badge&message=Google+Drive&color=4285F4&logo=Google+Drive&logoColor=FFFFFF&label=)](https://drive.google.com/file/d/1OjtpVegdbtQrV0KKWl9_DAS8M7Uys3Fx/view?usp=sharing)

After downloading the files, you can simply import the files directly into your Dataiku DSS. Happy exploring! ;)


## Introduction
1. Business Case: In the insurance industry, fraud is a major issue. It's tough to determine whether or not a claim is fraudulent. In this use case, I will use Dataiku DSS Platform to help the auto insurance industry to overcome this issue. 
2. Problem Statement: Data is housed in different systems, making it challenging to create analytics that incorporate multiple data sources. It takes a long time to copy data into a single platform.
3. Business Solution: Use S3 as a data lake to consolidate multiple data sources onto a single platform. Dataiku have capabillities to connect with multiple type of data sources like S3 bucket. This enables data scientists and analysts to examine data fast and generate reports in order to forecast market trends and/or make financial decision.
4. Technical Solution: Dataiku can be used as a single platform to gather data from API endpoints or batch dumps into S3 for additional processing. For efficient processing, ETL the CSV datasets into efficient Parquet formats.

## 📖 Problem Statements
This predictive model predicts the dataset from auto insurance either the claims is fraudulent or not. This will be a binary classification task and I will demonstrate few auto ML model using Dataiku DSS Platform like Logistic Regression, and Random Forest.

Based on the prediction data, the model are able to estimate the total predicted fraudulent claims (amounts), and break down the features of this fraudulent by looking fraud count by insured hobbies etc.

The steps covered to illustrate how ML Model Pipeline with Dataiku as follow:
1. Creating Project & Import the Dataset
2. Preparing Data with Recipes (Visual or Code)
3. Create Machine Learning Model
4. Zooming into the Prediction Data

## 📊 About the Dataset
To download the dataset, you may get it from [here](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/datasets/insurance_claims.csv).

This dataset collected from Auto Insurance in USA States, contains 1000 rows with 34 coloumns. Retrieved from [here]( https://github.com/mwitiderrick/insurancedata/blob/master/insurance_claims.csv)
<br/>
<br/>
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/dataset.png)

## 🧮 Algorithm
Two types of Machine Learning Model built in this project: Logistic Regressiona & Random Forest to compared both result of their accurancy. 

The Results shows that:
a) Random Forest shows ROC AUC 0.823 while Logistic Regressions shows ROC AUC results 0.820


## 🖥 The Flow
In DSS, the Flow is the visual representation of how data, recipes, and models work together to move data through an analytical pipeline. The Flow in DSS has an awareness of the relationships and dependencies between datasets in the project.
<br/>
<br/>
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/FLOW.png)

## 📊 Statistic Card 
In DSS, a Card is used to perform a specific Exploratory Data Analysis (EDA) task.
<br/>
<br/>
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/eda-card.gif)

The finding from this EDA, some string columns have many distinct values (900+). These columns should be removed from our dataset in the Data Processing step to improve model accuracy.

* policy number (1000 distinct)
* policy bind date (951 distinct. Possible to narrow down to year/month to test model accuracy)
* insured zip (995 distinct)
* insured location (1000 distinct)
* incident date (60 distinct. Excluding, but possible to narrow down to year/month to test model accuracy)


Like most of fraudulent dataset, the label of distribution is skewed.
<br/>
<br/>
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/Count%20by%20fraud_reported.png)

Data Processing take place to clean up the data a little and prepare it for our machine learning model. Removed the columns that identified earlier that have too many distinct categories and cannot be converted to numeric.

## 🤖 Create Machine Learning Model (Auto ML) & Analysed the Results - Training Models
### Model Overview
Image below shown the result of Machine Learning Models for Random Forest and Logistic Regression. Both Models shown the ROC AUC scores, where Random Forest shows the best scoring compared to Logistic Regression. So let's zoom into these result.
<br/>
<br/>
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/auto-ml.png)
 
### Model Summary
Let’s take a closer look at the results of the Random Forest model from these result. The Report page's Summary panel shows generic model information such as the algorithm and training date. In addition, the report page includes sections on model interpretation, performance, and extensive model information.
<br/>
<br/>
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/summary-ml.png)

### Model Interpretation
1. Decision Trees
-----------------
Dataiku have the ability to display the decision trees that underlying the model.
* The "proportions of target classes" describe the raw distribution of classes at each node of the decision tree
* The "probability" parameter reflects what would be expected if the node were a leaf


![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/decision-trees.png)


2. Variable Importance
----------------------
The Variables importance tab in the Interpretation section reveals the global feature importance of the model.

The parameters incident_severity is Major Damage, insured_hobbies is chess, and insured_hobbies is cross-fit shows the highest correlation with Fraudulent in Insurance Claims.

![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/v-i.png)

3. Partial Dependence
---------------------
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/pdgif.gif)

Partial dependency plots are a type of post-hoc analysis that may be performed after the model has been established.

A partial dependence plot shows the dependence of the predicted response on a single feature. The x axis displays the value of the selected feature, while the y axis displays the partial dependence.

The value of the partial dependence is by how much the log-odds are higher or lower than those of the average probability.


![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/pb1.png)


In the figure below, the relationship of the insurer age appears to be roughly parabolic with a minimum somewhere between ages 23 to 24 are highly tend to commit fraudulents. After the age of 30, the relationship is slowly decresing, until a precipitous dropoff in late age of 55.

Partial dependence plot of the Age feature reveals the likelihood of fraudulent claims increases incrementally with age of 60, which makes sense for these age to do fraudulents.


![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/pb2.png)

Note that for classifications, the predictions used to plot partial dependence are not the predicted probabilities of the class, but their log-odds defined as log(p / (1 - p)).

The plot also displays the distribution of the feature, so that you can determine whether there is sufficient data to interpret the relationship between the feature and target.

4. Subpopulation Analysis
-------------------------
Subpopulation analysis allows us to assess the behavior of the model across different subgroups.

Based on these subpopulation analysis, we can analyze the model performance based on incident_severity. The results show similar model behavior across incident severity, with a slight decrease in performance for total loss & major damage.


![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/subana.png)

5. Individual Explanations
--------------------------

Dataiku DSS allows to generate individual prediction explanations. The explanations picked from 3 most influential features for extreme probabilities. In this case, the most top 3 of most influential features are insured_hobbies, incident_severity and the vehicle_claim.

Based on the images below, the high probabilities of doing fraudulent is on the age of 39 which the probability is 0.950, where their hobbies is playing chess, the incident severity is minor damage and the vehicle claims is 61740.0. Apart from that, we can zoom in more about others features explanations for further details. 

![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/ie-1.png)

Individual explanations is the interesting part to analysed if you want to dig down of the probabilities of the individual result. You can get clear ideas how these individual explanations could predict characteristics or traits of a person who is highly tend to do fraudulents.

6. Interactive Scoring
----------------------
The interactive scoring simulator allows any AI builder or consumer to run "what-if" analyses like qualitative sensibility analyses to gain a better understanding of the impact changing a given feature value has on the prediction by displaying the resulting prediction and individual prediction explanations in real time.

In a fraud detection use case, this functionality allow to examine how altering the amount of a transaction changes the anticipated likelihood that it is a fraud.


![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/is-1.png)

### Model Performance

1. Confusion Matrix
-------------------

The Confusion matrix compares the actual values of the target variable with the predicted values

The Confusion matrix shows that the model has a **6% false-positive rate**, and **a Recall (true-positive rate) of 62%.**


![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/cm-1.png)

2. Decision Chart
-----------------
The Decision chart tab shows a graphical depiction of the model's performance data for each conceivable cut-off value.

The Decision chart also shows the location of the optimal cut-off (based on the F1 score), which is 0.38 for our Random Forest model.
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/dcc.png)

3. Lift Chart
-------------
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/lift-c.png)

4. Callibration Curve
---------------------
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/callibration-c.png)

5. ROC Curve
------------
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/roc-c.png)

6. Density Chart
-----------------
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/density-c.png)

7. Metrics & Assertations
-------------------------
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/metric.png)

### Model Information
1. Algorithm
-------------
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/algorithm.png)

2. Hyperparameter Optimization
------------------------------
![Alt Text](https://github.com/sulaihasubi/insurance-claims-fraud-detection/blob/main/images/hyperparameter.png)
