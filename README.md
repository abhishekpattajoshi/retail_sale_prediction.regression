# retail_sale_prediction.regression

![image](https://user-images.githubusercontent.com/131600014/233893204-895b7fcd-d664-4576-850e-53743f9990b0.png)

In this project I dealt with dataset named "Rossman Store" which is past data of Europe drug stores. I performed interactive exploratory data analysis to find the meaningful insights from dataset and used different machine learning algorithms to predict the sales.

Problem Objective

Rossmann operates over 3,000 drug stores in 7 European countries. Currently, Rossmann store managers are tasked with predicting their daily sales for up to six weeks in advance. Store sales are influenced by many factors, including promotions, competition, school and state holidays, seasonality, and locality. With thousands of individual managers predicting sales based on their unique circumstances, the accuracy of results can be quite varied.

Solution

Step 1: Data Wrangling: I got two datasets Rossmman Store Data and Stores dataset. I merged both the dataset and then cleaned it. There was lot of nan values in    dataset.
Column Competition OpenSinceMonth" and "CompetitionOpenSince Year" had nan values - after exploring got to know that I should replace the null values by mode because most of the values are month and year.
Column "Competition Distance" had nan values - after exploring got to know that should replace the null values by median because some values arre small and some are very high which can affect the mean.
Column Promo2SinceWeek", "Promo2Since Year, Promointerval" was having a lot of Null values, because those stores have not started any promotion, so they should be zero in the dataset.

Step 2: Exploratory Data Analysis: Explored the data to find insights and better understand the impact of variables on model learning. The insights of dataset are-
1)Stores are of 4 types a,b,c,d where a has maximum of 54.23% and b has minimum of 1.56%.
2)store has 3 assortment level a=basic, b=extra and c=extended.There are maximum of basic level store with 52.84% whereas extra level store is minimum with 0.82%.
3)61.85% of the stores are not running promo whereas 38.15% stores are running promos.
4)Out of those 38.15% who are running promo 50% of the store continues the promotion whereas 50% stopped.
5)Storetype b has highest number of sales.
6)Assortment level b has highest number of sales.
7)Average Sales by store Type -a : 5738
  Average Sales by store Type -b: 10058 
  Average Sales by store Type -c: 5723
  Average Sales by store Type -d : 5641
8)In the year 1900 the sale is highest because of low competition but as the year pass on the competition increases and sales decreases.
9)The sale in 2013 and 2015 is lowest despite promotion.This may be because of increase in competition year by year.
10)Sales on day1 which is monday is highest and it decreases day by day till day 6 which is saturday. It drastically decreases on day 7 because sunday most of the stores remains close.
11)In the month of january june and august the competion is most and lowest in the month of february and november. This may be because of new year in january and climate change in the month of june.
12)Store who took promotions there sale is higher compare to those who haven't opted for promotions.
13)Store which are open during the school holidays have more sale than the normal holidays. This may be because school may have holidays but other things are working as usual.

Step 3: Feature Engineering: Deriving new attributes based on the original variables to better describe the phenomenon that will be modeled.

Step 4: Machine Learning model training:There are some values in sales column whose values are 0.So we divided the dataset into 2 parts.One dataset which contains all the values including sales as 0 and another one excluding sales as 0.
We have applied Linear Regression, Lasso, Ridge, Decision Tree and XGBoost models.

Conclusion

XgBoost has the highest accuracy among all other models. So XGBoost is the best model for this dataset.By seeing both dataset we come to know that dataset including sales=0 have more accuracy compare to excluding sale=0 because lot of information went missing which affected the accuracy of model.So, we decided to keep all the datails of sales.
