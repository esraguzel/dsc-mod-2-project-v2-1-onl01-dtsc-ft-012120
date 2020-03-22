# Readme

In module 2 final project, the dataset 'kc_house_data.csv' is explored. The aim of this project is to provide assistance to the decision making of the buyers/investors who are new to King County. The two questions explored location and timing's importance when investing in a house. In addition, Multiple Linear Regression analysys peformed to provide accurate predictions for house prices. 

## Q1: What Are the Top Five Zip codes? How Does Location Affect House Prices?

### Exploration (EDA)
This question is asked to explore which part of the county is most expensive , how location affect house prices and the correlation between house prices and location. If there is high correlation between house price and location data, location data can be used as a predictor for linear regression analysis.  

For the first part of the question average price calculated for each zip code. During grouping the prices by zip codes, the `mean ()` function is used instead of `sum ()` to reach unbiased results. 

<img src="https://github.com/esraguzel/dsc-mod-2-project-v2-1-onl01-dtsc-ft-012120/blob/master/images/Screenshot%202020-03-22%20at%2000.24.12.png?raw=true" width="100%">

Secondly, direction column created from the latitude and longitude data to search how is average price distributed by directions. A scatter plot created with avaliable latitude and longitude data. To specify the four directions the scatter plot used as a base.

<img src="https://github.com/esraguzel/dsc-mod-2-project-v2-1-onl01-dtsc-ft-012120/blob/master/images/Screenshot%202020-03-22%20at%2012.05.12.png?raw=true" width="100%">



Four directions NW, NE, SE, SE calculated for each latitude and longitude combination and added to the dataframe. To further analyze location's effect on house prices an open source data 'zipcode_king_county.geojson' is loaded to work with folium. It is aimed to create a heatmap with `Choropleth()` function showing average price for each zip code.  

<img src="https://github.com/esraguzel/dsc-mod-2-project-v2-1-onl01-dtsc-ft-012120/blob/master/images/Screenshot%202020-03-22%20at%2013.39.12.png?raw=true" width="100%">


### Q1: Findings/Insights/Recommendations

#### Findings

- The top 5 zip codes by average price are 98039, 98004, 98040, 98112 and 98102.
- Location is one of the most important features in predicting house prices.
- As expected the northwest of the county has the highest price and highest variance.
- It can be concluded that the Bellevue, Seattle and Mercer Island have the highest average house prices.
- Northeast is the second in terms of highest price and variance.
- Southwest and Southeast parts of the county has lowest prices.
- The average price for northeast and northwest are almost the same.
- The average price of southeast is higher than southwest part of the county.


#### Recommendations

- The results showed that location has hight impact on house prices therefore location data can be used as a proxy to predict house prices.   
 
#### Next steps

- More concrete insights can be reached with broader datasets including features such as crime rates, distance to transportation and schools etc.  


## Q2: Which Season and Months Are Best to Buy A House?
The second question aims to answer which season and month is more affordable in terms of buying a house, as well as months and seasons role in predicting house prices. In order to answer our second question the 'month' and 'season' columns which are previously created and added to the dataframe are used. Furthermore, `groupby()` function is used to group data in months and seasons. During grouping the price by months and seasons, the `mean ()` function is used to reach unbiased results.

<img src="https://github.com/esraguzel/dsc-mod-2-project-v2-1-onl01-dtsc-ft-012120/blob/master/images/Screenshot%202020-03-22%20at%2012.57.25.png?raw=true" width="100%">

<img src="https://github.com/esraguzel/dsc-mod-2-project-v2-1-onl01-dtsc-ft-012120/blob/master/images/Screenshot%202020-03-22%20at%2014.18.19.png?raw=true" width="100%">

<img src="https://github.com/esraguzel/dsc-mod-2-project-v2-1-onl01-dtsc-ft-012120/blob/master/images/Screenshot%202020-03-22%20at%2012.57.25.png?raw=true" width="100%">

### Q2: Findings/Insights/Recommendations

#### Findings

- As predicted the best season to buy a house is winter.
- Fall has the highest price range followed by summer and spring.
- Spring has the highest average price followed by summer and fall.
- The average prices and median for each season are very close. Season is not genuine as expected to be used as a predictor in the regression model.
- While October has the highest variance, February has the lowest variance.
- February has the lowest, April has the highest price average.
- Like seasons there isn't a the big difference between the median values and average price for months.
- Month is also not an effective predictor for the regression model.


#### Recommendations

- The results showed that seaons and months has considerable low impact on house prices therefore season and month data cannot be used as an effective proxy to predict house prices.   
 

 
#### Next steps

- More concrete insights can be reached with broader datasets including a longer period of purchases. 


## Model Features

Baseline model uses 'is_renovated', 'waterfront','with_basement', 'view', 'condition', 'condition_4', spring, summer,'spring','summer', grade, 'sqft_living','sqft_lot','sqft_above','sqft_living15','sqft_lot15','bathrooms' and 'yr_built' to predict the house prices. Some of them are added as dummy variables to the dataframe. The baseline model explains variance for 61 %.

For refining the model zip codes and directions are added to the second model. With the location feature the model's R-squared value reaches to 87 %. To avoid multicollinearity 'sqft_above' value dropped and the R-squared value decreased by 0.001.

With Recursive Feature Elimination 70 features is chosen and the final model accounts for 85 % of the house prices.
Final model includes: 'vw_3', 'vw_4', 'condition_5', 'waterfront', 'gr_3', 'gr_4','gr_5', 'gr_6', 'gr_7', 'gr_8', 'gr_9', 'gr_10', 'gr_11', 'gr_12','bedroom_1', 'bedroom_2', 'bedroom_3', 'bedroom_4', 'bedroom_5', 'bedroom_6', 'bedroom_7', 'bedroom_8', 'bedroom_9', 'bedroom_10','bedroom_11', 'sqft_living', 'sqft_living15', 'yr_built', 'zip_98004', 'zip_98005', 'zip_98006', 'zip_98007', 'zip_98008','zip_98010', 'zip_98011', 'zip_98014', 'zip_98019', 'zip_98024','zip_98027', 'zip_98028', 'zip_98029', 'zip_98033', 'zip_98034','zip_98039', 'zip_98040', 'zip_98045', 'zip_98052', 'zip_98053','zip_98056', 'zip_98059', 'zip_98065', 'zip_98070', 'zip_98072','zip_98074', 'zip_98075', 'zip_98077', 'zip_98102', 'zip_98103','zip_98105', 'zip_98106', 'zip_98107', 'zip_98108', 'zip_98109','zip_98112', 'zip_98115', 'zip_98116', 'zip_98117', 'zip_98118','zip_98119', 'zip_98122', 'zip_98125', 'zip_98126', 'zip_98133','zip_98136', 'zip_98144', 'zip_98146', 'zip_98155', 'zip_98166','zip_98177', 'zip_98199' columns.

Cross validation is performed for each model trained using 5 folds. As R-squared and root mean squared error values for Model 1, Model 3 and Model 5 are consistent with our final model that we have trained using train-test split process, we can conclude that our feature and model selection process is validated.

The final model's mean squared values for test and train sets indicates that the final model is not ovetfitting or underfitting.


