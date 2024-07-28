A project I worked on as a part of Regression Certification from Maven Analytics where I used Linear Regression and Ridge Regression to predict fuel prices. 

**Data**: 

<img width = "900" align= "center" src = "https://github.com/user-attachments/assets/6d68f13e-57cb-4012-aa04-2c0382795a5f"> </img>

Rows: 398, Columns: 9

**Column Description:**
1. mpg - refers to miles per gallon. It is the dependent variable in this project.
2. cylinders - Number of cylinders in a vehicle
3. displacement - engine displacement of the vehicle
4. horsepower - horsepower of vehicle's engine
5. weight - weight of the vehicle
6. acceleration - Speed of the vehicle
7. model year - the year of manufacturing of the car. It is typically from 1970 to 1982
8. origin - origin of the vehicle. 1 represents Americas, 2 represents EU and 3 represents Japan
9. car name - Name of the car

**Steps:**

1. Data Cleaning - Dealing with NaNs, data inconsistencies, typecasting for data manipulation. One major issue I found out at this stage was usage of '?' character for a few missing values within the column horsepower. To deal with it, I imputed mean of the column as the problem was within 6 rows only.
3. EDA - Conducted an exploratory data analysis to understand the data and relationships between features through pairplots and correlation.
<img width = "600" align= "center" src = "https://github.com/user-attachments/assets/25504eab-00c2-4b3d-bf78-d4890edc152f" > </img>
As indicated by the correlation plot above, we can already see that there's strong correlation between the features. As such, we'd probably have to add a polynomial term to the independent variables for predicting mpg without violating the Linearity assumption.
4. Creating a baseline model - Created a linear model using the highest correlated variable **weight** to predict **mpg**. With just one feature we got the following results which were expected.
<img width = "450" align= "center" src = "https://github.com/user-attachments/assets/bdb4de61-accf-41cf-b55b-4c934ebe3a9e"> </img>
5. Performing Feature Engineering: By this stage, I knew about multicollinearity existing within the model, hence to avoid violation of assumption of Linearity, I added a polynomial variable before the multiple regression stage. I also created dummy variables out of origin column. 
6. Multiple Linear Regression - At this stage I initially used all features and then narrowed down to top 5 features depending on the p-value and statistical significance. With **weight, weight2, model_year, origin2, origin3**, I was able to produce a good model, that didn't violate any assumptions of Linear Regression and produced a test R-squared value of 81.5%.
7. Trying Ridge Regression for Comparison: With multicollinearity between the features, while I had already cleaned up the features for Linear Regression, I used Ridge to assess if it would yeild better results. With all features, I did get an improved R-squared and MAE but to keep the model simple, it's better to go with Linear Regression with 5 features. 
   
