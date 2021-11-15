# Insurance Claim - Fraud Detection with Dataiku DSS
[![Dataiku](https://img.shields.io/static/v1?style=for-the-badge&message=Dataiku&color=2AB1AC&logo=Dataiku&logoColor=FFFFFF&label=)](https://www.dataiku.com/)
[![Kaggle](https://img.shields.io/static/v1?style=for-the-badge&message=Kaggle&color=222222&logo=Kaggle&logoColor=20BEFF&label=)](https://www.kaggle.com/)
[![GitHub](https://img.shields.io/static/v1?style=for-the-badge&message=GitHub&color=181717&logo=GitHub&logoColor=FFFFFF&label=)](https://github.com/sulaihasubi)

## About this Project
Since Github have limitation of size to support the files upload, you can explore about this project with Dataiku DSS by downloading the file with the link provided as below:
<br/>
<br/>
[![Google Drive](https://img.shields.io/static/v1?style=for-the-badge&message=Google+Drive&color=4285F4&logo=Google+Drive&logoColor=FFFFFF&label=)](https://drive.google.com/file/d/1OjtpVegdbtQrV0KKWl9_DAS8M7Uys3Fx/view?usp=sharing)

After downloading the files, you can simply import the files directly into your Dataiku DSS


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
