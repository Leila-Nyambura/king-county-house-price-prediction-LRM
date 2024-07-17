# Project 2 (Group Work)

# King County House Price Prediction using Linear Regression Model

## Project Overview

## Data Source
This project utilizes the King County House Sales dataset, which is available in `kc_house_data.csv` located in the `data` folder of this repository.

## Business Understanding

## Introduction
The real estate market is a dynamic and complex field influenced by numerous factors that affect property values. Predicting house prices accurately is crucial for buyers, sellers, real estate agents, and investors to make informed decisions. This project aims to develop a linear regression model to predict house prices using a variety of independent variables, including physical attributes of the properties, location-based features, and other relevant factors. By leveraging data analysis and machine learning techniques, this project seeks to provide a robust tool for estimating property values, thereby enhancing decision-making processes in the real estate sector.

## Problem Statement
Accurately predicting house prices is a significant challenge due to the multitude of variables that can influence property values. Traditional methods often fail to capture the complexity and interactions between different factors, leading to less reliable predictions. This project addresses the problem of developing a reliable and accurate predictive model for house prices using linear regression, incorporating a comprehensive set of independent variables to improve prediction accuracy.

## Objectives

Explore the Relationship Between Property Size and Housing Prices:
Investigate how the size of a house correlates with price. Determine if larger properties command higher prices, aiding real estate investors in valuation strategies.

## Develop a Linear Regression Model to Predict Housing Prices:

Build and evaluate a linear regression model using features bedrooms, bathrooms,sqft_living,grade, condition,sqft_lot,floors, waterfront,yr_built. Provide stakeholders with a predictive tool for estimating housing prices and supporting strategic decision-making in urban development.

## Column Names and Descriptions for Kings County Data Set
id - unique identifier for the house

date - date the house was sold

price - is prediction target

bedrooms - number of bedrooms

bathrooms - number of bathrooms

sqft_livingsquare - square footage of the home

sqft_lotsquare - square footage of the lot

floors - number of floors in the house

waterfront - does the house have waterfront view?

view - has the house been viewed?

condition - How good is the overall condition is of the house?

grade - overall grade given to the housing unit, based on King County grading system

sqft_above - square footage of house apart from basement

sqft_basement - square footage of the basement

yr_built - year house was built

yr_renovated - year when house was renovated

zipcode - area zip code

lat - latitude coordinate

long - longitude coordinate

sqft_living15 - The square footage of interior housing living space for the nearest 15 neighbors

sqft_lot15 - The square footage of the land lots of the nearest 15 neighbors

### Columns dropped:
- date
- view
- sqft_above
- sqft_basement
- yr_renovated
- zipcode
- lat
- long
- sqft_living15
- sqft_lot15

## Data Analysis and Visualizations

#### Checking how the size of the house compares to its price

![image](https://github.com/user-attachments/assets/749d3795-6498-4cf9-baa0-110a9655d494)


#### Impact of the quality of construction and design of a house(grade) on the price of the house
![image](https://github.com/user-attachments/assets/4c98a8ec-8fd8-407c-8b60-759a517078c8)

## Feature Selection

#### Visualizing the dataset using a pairplot to explore correlations and distributions

![image](https://github.com/user-attachments/assets/81bb2769-2e2e-4db9-bcac-055687f9e34a)


### Visualizing the correlation using a heatmap
![image](https://github.com/user-attachments/assets/8ed535ac-e0ad-43eb-aa54-95641be8b5b9)

#### Checking the correlation between the independent variables to the price(our target variable)

![image](https://github.com/user-attachments/assets/837621c0-c93c-4c8c-b191-635a2bb51a8d)

![image](https://github.com/user-attachments/assets/b0667df3-7e19-434c-8c6a-b00296159980)

### Checking for Outliers
![image](https://github.com/user-attachments/assets/9c22c28d-bb2c-40d8-bf77-a928d44338b8)

Features Used: 'price', 'bedrooms', 'bathrooms', 'sqft_living', 'sqft_lot', 'floors',
       'has_waterfront', 'condition', 'grade', 'is_renovated', 'age'

We decided to use all features (except those we initially dropped). Then tested the features practically to create the most accurate model, leveraging on the information from the correlation matrix. 
Priority features will be those that have a strong correlation with the price


















