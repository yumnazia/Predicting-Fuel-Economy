A project I worked on as a part of Regression Certification from Maven Analytics where I used Linear Regression and Ridge Regression to predict fuel prices. 
This included;
1. Data Cleaning - Dealing with NaNs, data inconsistencies, typecasting for data manipulation
2. EDA - Conducted an exploratory data analysis to understand the data and relationships between features through pairplots and correlation.
   ![image](https://github.com/user-attachments/assets/25504eab-00c2-4b3d-bf78-d4890edc152f)

3. Creating a baseline model - Created a linear model using the highest correlated variable **weight** to predict **mpg**. With just one feature
   we got the following results which were expected.
   ![image](https://github.com/user-attachments/assets/bdb4de61-accf-41cf-b55b-4c934ebe3a9e)
4. Performing Feature Engineering: By this stage, I knew about multicollinearity existing within the model, hence to avoid violation of assumption of
   Linearity, I added a polynomial variable before the multiple regression stage. I also created dummy variables out of origin column. 
5. Multiple Linear Regression - At this stage I initially used all features and then narrowed down to top 5 features depending on the p-value and
   statistical significance. With **weight, weight2, model_year, origin2, origin3**, I was able to produce a good model, that didn't violate any assumptions
   of Linear Regression and produced a test R-squared value of 81.5%.
6. Trying Ridge Regression for Comparison: With multicollinearity between the features, while I had already cleaned up the features for Linear Regression,
   I used Ridge to assess if it would yeild better results. With all features, I did get an improved R-squared and MAE but to keep the model simple, it's better
   to go with Linear Regression with 5 features. 
   
