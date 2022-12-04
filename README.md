# Bike Sharing Demand Prediction
Bike-sharing system is a shared micro-mobility service for short term bike rental. The service can be free of charge (e.g., paid by a city) or offered for a price. In many cities, renting a bike has become an everyday digital service. For unlocking the bike, the users only need a subscription card or their smartphone. The users can leave the bikes to suitable docking stations or areas.

## Table of Content
  * [Objective](#objective)
  * [Dataset](#dataset)
  * [Technical Aspect](#technical-aspect)
  * [Installation](#installation)
  * [Project Structure](#project-structure)
  * [Tools Used](#tools-used)
  * [Performed Model Result](#performed-model-Result)
  * [Project Summary](#project-summary)
  * [Conclusion](#conclusion)

## Objective
The project goal is to minimize the waiting time or make rental bike available at the right time, so company want to predict the bike count required at each hour for the stable supply.

## Dataset
The dataset contains web scraped data shows hourly rental for one year from “December,2017” to   “November,2018” from "Seoul city" bike counting detailes for analysing the Bike sharing market. 

Data include weather information (Temperature, Humidity, Windspeed, Visibility, Dewpoint, Solar radiation, Snowfall, Rainfall), the number of bikes rented per hour and date information. More details of the dataset can be found in the kaggle website.https://www.kaggle.com/datasets/saurabhshahane/seoul-bike-sharing-demand-prediction#SeoulBikeData.csv

## Technical Aspect
This project is divided into three parts.
1. Exploratry Data Analysis
      - Exploratory data analysis is an important step that starts once business hypothesis is ready. This step takes 40-50% of total project time as the model outcome depends on the quality of input data being fed to train the model. Exploratory data analysis involves data attributes identification, data preprocessing and feature engineering.
2. Feature Engineering 
      - Feature engineering is the pre-processing step of machine learning, which is used to transform raw data into features that can be used for creating a predictive model using Machine learning or statistical Modelling. Feature engineering in machine learning aims to improve the performance of models. 
2. Model Building
      - Building an ML Model requires splitting of data into two sets, such as ‘training set’ and ‘testing set’ in the ratio of 80:20 or 70:30; A set of supervised (for labelled data) and unsupervised (for unlabeled data) algorithms are available to choose from depending on the nature of input data and business outcome to predict.

## Installation
This project requires python 3.6 or any other higher versions of python.
This project need software to run this python notebook "Jupyter Notebook" or "Google colab". It is highly recommended that you install the Anaconda distribution of Python or use "Google Colab" https://colab.research.google.com/, which already has most of the above packages and more included.
 

## Project Structure
```
├── README.md
├── Dataset 
│   ├── SeoulBikeSharing.csv 
│
│
├── EDA
|   ├── Data Cleaning
│       ├── Duplicated values
│       ├── NaN/Missing values
│   ├── Numeric & Categoric features
│   ├── Treating Skewness
│   ├── Treating Outlier 
│   ├── Univariate & Bivariate Analysis
│   ├── Multivariate Analysis
│
├── Feature Engineering
│   ├── Handling Multicollinerity
|       ├── Correlation
|       ├── VIF analysis
│   ├── Encoding
|       ├── Ordinal Encoding
|       ├── One-Hot Encoding
│
├── Model Processing
│   ├── Train Test Split
│   ├── Scaling - Standrdization
│   ├── Model selection
│   ├── Hyperparameter Tunning
│   ├── Model Explainability
|
│   
├── Report
├── Presentation
├── Result
└── Reference
```

## Tools Used
![image](https://user-images.githubusercontent.com/112171582/205482290-ed2f9a20-5bb6-494e-aed4-6a8fb29fdb7e.png)

## Performed Model Result
![image](https://user-images.githubusercontent.com/112171582/205483391-c02384ac-d657-4e9e-97c7-9690d0b666ac.png)

## Project Summary
**The project goal is to minimize the waiting time or make rental bike available at the right time, so company want to predict the bike count required at each hour for the stable supply.**

* Given dataset have past records of bike count during a day based on weather condition, season, holiday and functional day.
* Performing EDA on data to understand how independent variable behave with dependent variable.
* Checking multicollinearity because after plotting heatmap correlation we understood there are two independent variables strongly corelate with each other, for that we calculate the VIF then dropping the one of the feature.
* For data preparation the categorical features convert by using one hot encoding or label encoding.
* Important features selection and building a models to finalize final model based on r2 score and RMSE score after that tune the hyperparameter.
* Most Important feature results have shown that Temperature and Hour of the day are most influence variable in hourly rented bike demand prediction.
* We get best r2 score and low root mean square error from LGBM_tuning model.
* To understand how affecting the feature for best model results we use shaply for model explainability.

## Conclusion
In this EDA the given datasets are analysed and several graphs has been plotted which can be used to give more insights to the dataset.
* Working or Non-working Day - We see 2 rental patterns across the day in bike rentals count.
First for a Working Day where the rental count high at peak office hours (8am and 5pm).
Second for a Non-working day where rental count is uniform across the day with a peak at around noon.
* Temperature: People generally prefer to bike at moderate to high temperatures. We see highest rental counts between 30 to 35 degrees Celsius.
* Hour: Demand of rental bike is high at Evening time in between 4PM to 8PM.
* Weather: As one would expect, we see highest number of bike rentals on a clear day and the lowest on a snowy or rainy day.
* Season: Demand of rental bikes is high during Summer and Autumn season.
* Humidity: With increasing humidity, we see decrease in the number of bike rental count.

The dataset contains possibilities to deliver insights to understand bike sharing demands better and thus help to popularize bike sahring demand.  Finally we are selecting **LGBM(Light Gradient Boosting Algorithm)** model as our final model. So, in future if we want to do some prediction with this data then the LGBM model will fit perfectly to do the prediction with the **highest R2 score and lowest RMSE value**.
