# Repository for DATA 606
# DATA 606 FINAL PROJECT REPORT

# USED CARS PRICE PPREDICTION

## COLLABORATORS

1. JASWANTH SAI NATHANI
2. SAIDA BABU GARLAPATI



## PROJECT OVERVIEW

* Introduction
* Data Collection
* Data Cleaning
* Exploratory Data Analysis
* Prediction Modelling
* Application Design




## INTRODUCTION

### Motivation

* The manufacturer sets the price of new cars in the industry, with the government incurring some additional costs in the form of taxes. Due to rising new car prices, used car sales are on the rise worldwide. However, because of the affordability of used cars, people tend more purchasing the used cars.

* When purchasing and selling, it's critical to understand the true market value of a car. A used car price prediction system is needed to accurately estimate the cars’ worthiness based on the features. While there are websites that provide this service, their forecast approach may or may not be more accurate. So, several methods and algorithms may be required in the prediction of a used car's true market worth.

* As a result, the model established in this study could aid online web services that determine the market worth of a used car. Many people are interested in the used automobile market because they wish to sell their car or buy a used car at some point in their lives. 

* It's a great mistake to pay too much or sell for less than the market worth in this process so it is important to understand the price.




### Problem Statement


* The goal of this project is to estimate the price of used cars in the USA, using various machine learning techniques. 

* For the benefit of buyers and sellers, a predictive analysis on used car prices and an estimation of what would be a good price to buy or sell a car on the open market.

* Try to make an estimate as to what features of a car matters most, in determining a used car's pricing.
 

### Approach

* Data extraction using web scraping of website with used car data (eg: https://www.truecar.com ) and then proceed with data cleaning and feature selection. Also, once data cleaning is done would like to understand how various features are distributed and try normalizing them if required.

* Developing a regression model to predict the price of used car based on various models like linear regression model, random forest and Gradient boosting model and cross validating the results to find the best fit model for price prediction in the case of both test and train data.

* Designing a web page to demonstrate the working of best fit model and provide an easy and interactive way to the user to predict the car price based on a few questions.




## DATA COLLECTION

* Web Scraping of TRUECAR website for used car listings across United States.

* Extracting the dataset with listings of 10173 cars after considering the car listings of 333 pages.

* Dataset having 18 columns like :
          VIN, Brand, Model, Trim, Manufacture Year, Mileage, MPG_City, MPG_Highway, Drive Type, Fuel Type, Transmission, Exterior Color, Interior Color,           Accidents, Number of Owners, Car Usage Type, Location, Price.


## DATA CLEANING

* After loading the dataset, the shape of the dataset is (10173, 18).

* We have to check for duplicates, null values and the data types.

* As VIN is unique for every car, we filter the listings by VIN to eliminate the duplicate values.

* As there are null values in MPG, transmission, drive type, fuel type and price, we impute them.

* All the data types are good except mileage and price, so we find the wrong data and correct them.


#### Duplicates:

* There are 9899 unique VIN, which determines the data contains 274 repeated car listings. After deleting the duplicates, the shape of the dataset is (9899, 18).

#### Null Values:

* As we see there is one null value in ‘Price’, we delete that listing as our main target variable is price.

* For filling missing values in ‘drive_type’, we try to get drive_type from ‘trim’ column and impute to the corresponding data.

* After sorting the data based on brand and model, picking up the missing values columns and imputing them with a forward fill and backfill of existing values in the corresponding columns.

#### Data Types:

* After imputing the null values, the data types of mileage and price automatically corrected.


#### Addition of features:

* Added a new feature ‘Car_Age’, which is obtained by subtracting manufacture year from current year. And also checking if there are any car listings with manufacture year greater than 2022. Fortunately, there are no listings in that category.

* Removed the ‘Location’ column from the dataset, and added ‘State’ column by splitting the location and extracting the state from that.

* Adding a new feature ‘MPG’, which is obtained by the average of MPG_City and MPG_Highway values.


## EXPLORATORY DATA ANALYSIS

After clear analysis of the data, it is observed that we have:
* Vehicles from 49 different states across United States with 41 different branded cars.

* Vehicle models with manufacture years from 1997 - 2022 and Mileage ranging from 5 miles to 266229 miles.

* Cars with a minimum price of 2995 and maximum upto 272990 dollars.

* 11 columns with numerical values, 6 columns with integer values and 1 column with float values.

#### Listings as per State:

* From this we can clearly see that texas stands in the first position in the number of listings with 2162 (21.8%) and next is florida with around 1532 (15.5%) car listings and california has 1187(12%) he least number of cars being posted online from  the state of Maine which is just 3 listings 

#### Listings as per Brand:

* Ford is the dominant brand on the used car market. And Chevrolet, Toyota, Jeep, Nissan are another top 4 makers. Totally they account for about 46% of the used car listings.

* Almost 96% of the car listings are with fuel type as Gas and only few cars are Hybrid, Diesel and Electric


* Most of the cars have automatic transmission


* A hypothesis here that used car website publishes cars with accident history is wrong, as most of the cars are with no accidents



## PREDICTIVE MODELLING

### LINEAR REGRESSION MODEL

* This model we have processed the data using ohe and standard scaler, we got a train accuracy of 92.16 and test accuracy of 91.24 which is very good scores and most of the data looks to be linear.

* Also the RMSE for this model are 4681.508 (train data), 4814.534 (test data)


### RANDOM FOREST MODEL

* Using Random Forest Model we got very good train score but the testing score is very less, this might be because the model is trying to overfit the data which sometimes is common in RF models. 

* Steps Taken to reduce this overfitting:

1. Hypertune this model

2. We also learned that RF model does not go well with ohe so we tried label encoding the columns and trained the model with hyertune parameters but the results were not much different than earlier ones.


### GRADIENT BOOST MODEL	

* We used gradient boost model as It relies on the intuition that the best possible next model, when combined with previous models, minimizes the overall prediction error. 

* This model solved the problem of overfitting as the test and train scores difference is significantly less than the previous models.(Hypertuned model)

### XG BOOST MODEL

* This model performs good both for training and test data the root mean squared error is less than all the other models we have trained.
Problem in this model is even though it is hypertuned this model is also slightly overfitting which we can see from the RMSE values of test and train data


## CONCLUSION

* Considering all the RMSE values all the models for test and train data we choose to use the gradient boost model for predicting the price of the car. This takes the inputs of car brand, model, mileage, car age, drive type, fuel type, number of accidents and owners, to predict the price of the car



## APPLICATION DESIGN

* The web application was designed with the help of Streamlit and also Flask displayig the input of the user for car brand, model, mileage, car age, drive type, fuel type, number of accidents and owners. After all the details are entered the web site displays the predicted price of the car.




## TEAM RESPONSIBILITIES

### Saida Babu Garlapati: 
* Web Scraping the cars portal
* Data collection and extracting the dataset 
* Initial Cleaning of the data
* Exploratory Data Analysis
* Developing a web design for user friendly prediction

### Jaswanth Sai Nathani:
* Performing Data Modeling
* Checking different prediction models
* Model comparision and Cross validating the results
* Finding a best fit model for prediction
* Developing a web design for user friendly prediction


## PROJECT PPT LINK : https://github.com/iamsaida/Team_A_DATA606/blob/main/PPT/USED%20CAR%20PRICE%20PREDICTION.pptx

## PRESENTATION RECORDING YOUTUBE LINK : https://youtu.be/64MmvXDLugs
