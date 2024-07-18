# Project 2 (Group Work)

# King County House Price Prediction using Linear Regression Model

## Project Overview

## Data Source
This project utilizes the King County House Sales dataset, which is available in `kc_house_data.csv` located in the `data` folder of this repository.

## Business Understanding

## Introduction
The real estate market is a dynamic and complex field influenced by numerous factors that affect property values. Predicting house prices accurately is crucial for buyers, sellers, real estate agents, and investors to make informed decisions. This project aims to develop a linear regression model to predict house prices using a variety of independent variables, including physical attributes of the properties, location-based features, and other relevant factors. By leveraging data analysis and machine learning techniques, this project seeks to provide a robust tool for estimating property values, thereby enhancing decision-making processes in the real estate sector.

## Problem Statement
Homeowners and real estate agents often face the challenge of accurately predicting home values and identifying which renovations will yield the highest return on investment. Inaccurate valuations can affect home sales and lead to significant losses for both buyers and sellers. Uninformed renovation decisions can result in unnecessary expenditures without a corresponding increase in property value. For a real estate agency that helps homeowners buy and sell homes, providing accurate home valuations and precise advice on effective renovations is crucial. Traditional methods often fail to capture the complexity and interactions between different factors, leading to less reliable predictions. This project addresses the problem of developing a reliable and accurate predictive model for house prices using linear regression, incorporating a comprehensive set of independent variables to improve prediction accuracy.

## Objectives
1. Develop a model that accurately predicts the value of a house based on its features.

   Investigate the most important features in homes to create an accurate model for 
   estimating home value.
   
3. Explore and quantify the relationship between renovations and property value and refine 
   the model based on the results.

   Determine whether renovations affect home prices. If a relationship exists, quantify it and 
   refine the model to improve accuracy.
 
4. Offer tailored recommendations to homeowners based on their property characteristics and market conditions.

   Provide homeowners with accurate property valuations and advise on whether renovations would 
   be a worthwhile investment if they intend to sell.

## Data Understanding

#### Column Names and Descriptions for Kings County Data Set
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

#### Checking for Outliers
![image](https://github.com/user-attachments/assets/9c22c28d-bb2c-40d8-bf77-a928d44338b8)


Features Used: 'price', 'bedrooms', 'bathrooms', 'sqft_living', 'sqft_lot', 'floors',
       'has_waterfront', 'condition', 'grade', 'is_renovated', 'age'


We decided to use all features (except those we initially dropped). Then tested the features practically to create the most accurate model, leveraging on the information from the correlation matrix. 


Priority features are those that have a strong correlation with the price

## Model Creation, Evaluation and Validations
### Model 1. Analysis 1
#### A Simple Linear Regression Model

Simple Linear Regression Formula

The feature used for this model is 'sqft_living' and the predictor variable, 'price'

The formula for predicting the price (y) can be expressed as: y = β0 + β1 * sqft_living Where:

β0 is the intercept
β1 is the coefficient for sqft_living
Placing the values of the intercept and coefficient, the formula can be expressed as:

y = 158956.01 + 158.97582529 * sqft_living


Mean Squared Error: 26997058887.541637

Mean Absolute Error: 132831.78109333402

R Squared: 0.35426536920193596


Explanation:
Intercept (142832.55): This is the estimated price when the square footage of the living space is zero. It serves as the baseline price of a house without considering its size.

Coefficient (169.59): This represents the increase in price for each additional square foot of living space. For every extra square foot, the price is predicted to increase by approximately 169.59 units of currency.

Performance Interpretation:
The MSE value of 26,997,058,887.54 indicates that there is a significant average squared error between the actual and predicted prices. This suggests that there is room for improvement in the model.
The MAE value of 132,831.78 tells us that, on average, our model's predictions are off by about 132,831.78 units of currency.
The R² value of 0.35 means that 35% of the variability in house prices is accounted for by the model based on square footage alone. This indicates a moderate level of explanatory power, but it also suggests that other factors not included in this model are influencing house prices.
In summary, while this simple linear regression model provides a basic understanding of how house prices vary with the size of the living area, its performance metrics indicate that it may not be sufficiently accurate for precise predictions. Including additional features could potentially improve the model's accuracy.


### Model 2. Analysis 2

To improve the performance of our model, we shall add other key features in our simple model and evaluate its performance

#### Multiple Linear Regression Model

Using the top 5 features i.e 'sqft_living', 'grade', 'bathrooms', 'bedrooms', 'floors'
The formula for predicting the price (y) can be expressed as:

y = β0 + β1 * sqft_living + β2 * grade + β3 * bathrooms + β4 * bedrooms + β5 * floors

Where:

β0 is the intercept
β1, β2, ..., β5 are the coefficients for each feature
Placing the values of the intercept and coefficients, the formula can be expressed as:

y = -271416.9668649424 + 118.81604097 * sqft_living + 80470.38579525 * grade + -18220.19031844 * bathrooms + -12892.82031154 * bedrooms + -7053.33250738 * floors

Mean Squared Error of Model:  23757545024.29692
Mean Absolute Error of Model: 122306.04934670829
R Squared Value of Model: 0.43175033884849523

Explanation:
Intercept (-271416.97): This is the estimated price when all the predictors (sqft_living, grade, bathrooms, bedrooms, floors) are zero. It serves as the baseline price of a house without considering these features.

Performance Interpretation:
The MSE value of 23,757,545,024.30 indicates a significant average squared error between the actual and predicted prices, though it is slightly lower than the simple linear regression model, suggesting a better fit.
The MAE value of 122,306.05 tells us that, on average, our model's predictions are off by about 122,306.05 units of currency.
The R² value of 0.43 means that 43% of the variability in house prices is accounted for by the model based on the features included. This indicates an improvement over the simple linear regression model and suggests that including multiple features provides a better explanation of house prices.

In summary, this multiple linear regression model provides a more comprehensive understanding of how various features influence house prices compared to the simple linear regression model. However, the performance metrics indicate that there is still room for improvement, and incorporating additional relevant features might further enhance the model's accuracy



### Model 3. Analysis 3

#### Multiple Linear Regression Model
Using all features
The formula for predicting the price (y) can be expressed as:

y = β0 + β1 * sqft_living + β2 * grade + β3 * bathrooms + β4 * bedrooms + β5 * floors + β6 * has_waterfront + β7 * is_renovated + β8 * sqft_lot + β9 * condition + β10 * age

Where:

β0 is the intercept
β1, β2, ..., β10 are the coefficients for each feature
Placing the values of the intercept and coefficients, the formula can be expressed as:

y = -722928.656182566 + 110.32036 * sqft_living + 105666.687 * grade + 25011.2847 * bathrooms + -15618.9331 * bedrooms + 16338.1883 * floors + 278527.067 * has_waterfront + 7347.24504 * is_renovated + -7.35820112 * sqft_lot + 21879.1947 * condition + 2690.50331 * age

Mean Squared Error of Model:  18203549025.413246
Mean Absolute Error of Model: 105665.88359227464
R Squared Value of Model: 0.5645947190727462

Explanation:
Intercept (-722928.66): This is the estimated price when all the predictors are zero. It provides a baseline price of a house without considering these features.

#### Advantages of This Model:
Higher R² Value: With an R² value of 0.56, this model explains a significant portion of the variance in house prices, making it more reliable than the previous models.
Lower Errors: Both the MSE and MAE are lower in this model compared to previous ones, indicating more accurate and reliable predictions.
Comprehensive Features: By including multiple relevant features, this model provides a more detailed and nuanced understanding of how different factors affect house prices, leading to better-informed decisions for stakeholders.
In summary, this final multiple linear regression model offers improved predictive accuracy and reliability by incorporating a broader range of features. This makes it a valuable tool for predicting house prices and making informed real estate decisions.


## Recommendations Based On Analysis

### Relationship Between Analysis and Property Value
Determining whether renovations affect home prices and to what extent.

Comparing using measures of central tendency

![image](https://github.com/user-attachments/assets/ecd2b2f5-734b-46de-b6c7-bdfb3cc3fcff)

#### Explanation
In order to bring out their differences clearly, we shall compare the formula of predicting the value with and without renovations

From model 3 above the formula of the home price, y is: y = -749131.0488568435 + 113.872587 * sqft_living + 110635.642 * grade + 25545.2854 * bathrooms + -20906.265 * bedrooms + 15106.3867 * floors + 260503.41 * has_waterfront + 9452.40388 * is_renovated + -7.4194231 * sqft_lot + 20940.4675 * condition + 2763.58649 * age

Thus it can be seen that 9452.40388 is the coefficient for is_renovated

We can therefore conclude that renovations impact the valuation of a home positively.
According to our predictive model, renovation of a home improves its value by approximately 9500,if the other features of a house are held constant.
This shows that renovated houses have better sale prices on average.

## Conclusions
Objective 1:
Explore the Relationship Between Property Size and Housing Prices Conclusion:

Findings: The analysis reveals a strong positive correlation (r = 0.701917) between sqft_living (measured by footage of a house) and housing prices (price). Larger houses in terms of sqft_living tend to command higher prices. Implications: This correlation suggests that property size significantly influences housing prices, guiding decisions for real estate investors and homebuyers regarding property valuation and market positioning.

Findings: The analysis reveals a strong positive correlation (r = 0.695) between property size (measured by average number of rooms, RM) and housing prices (MEDV). Larger properties tend to command higher prices in the Boston housing market.
Implications: This correlation suggests that property size significantly influences housing prices, guiding decisions for real estate investors and homebuyers regarding property valuation and market position


Objective 2:
Develop a Linear Regression Model to Predict Housing Prices Conclusion:

Findings: The linear regression model, incorporating features bedrooms,bathrooms,sqft_living,grade,condition,sqft_lot,floors,waterfront,yr_built achieves an R-squared (R2) score of 0.51 on the test set. This indicates that 51% of the variance in housing prices (price) can be explained by these predictors. Implications: Stakeholders can utilize this model for predicting housing prices based on property characteristics. It supports informed decision-making in real estate investments, pricing strategies, and urban development planning.

Conclusion:

Findings: The analysis reveals a strong positive correlation (r = 0.695) between property size (measured by average number of rooms, RM) and housing prices (MEDV). Larger properties tend to command higher prices in the Boston housing market.
Implications: This correlation suggests that property size significantly influences housing prices, guiding decisions for real estate investors and homebuyers regarding property valuation and market position













