# Customer Personality Segmentation: Project Overview 
This project is a segmentation on a company's customers to learn the customer's information and behavior so the company could improve their knowledge of their customers and make better decisions.

Link to the dataset: https://www.kaggle.com/imakash3011/customer-personality-analysis

# Code and Libraries Used
* Python Version: 3.9.5
* Packages: NumPy, pandas, Matplotlib, seaborn, scikit-learn

# Columns 
* ID: customer's unique identifier
* Year_Birth: customer's birth year
* Education: customer's education level
* Marital_Status: customer's marital status
* Income: customer's yearly household income
* Kidhome: Number of children in customer's household
* Teenhome: Number of teenagers in customer's household
* Dt_Customer: Date of customer's enrollment with the company
* Recency: Number of days since customer's last purchase
* Complain: 1 if customer complained in the last 2 years, 0 otherwise
* MntWines: Amount spent on wine in last 2 years
* MntFruits: Amount spent on fruits in last 2 years
* MntMeatProducts: Amount spent on meat in last 2 years
* MntFishProducts: Amount spent on fish in last 2 years
* MntSweetProducts: Amount spent on sweets in last 2 years
* MntGoldProds: Amount spent on gold in last 2 years
* NumWebPurchases: Number of purchases made through the company’s web site
* NumCatalogPurchases: Number of purchases made using a catalogue
* NumStorePurchases: Number of purchases made directly in stores
* NumWebVisitsMonth: Number of visits to company’s web site in the last month
* NumDealsPurchases: Number of purchases made with a discount
* AcceptedCmp1: 1 if customer accepted the offer in the 1st campaign, 0 otherwise
* AcceptedCmp2: 1 if customer accepted the offer in the 2nd campaign, 0 otherwise
* AcceptedCmp3: 1 if customer accepted the offer in the 3rd campaign, 0 otherwise
* AcceptedCmp4: 1 if customer accepted the offer in the 4th campaign, 0 otherwise
* AcceptedCmp5: 1 if customer accepted the offer in the 5th campaign, 0 otherwise
* Response: 1 if customer accepted the offer in the last campaign, 0 otherwise

# Data Cleaning
After importing the data, I needed to clean it up by doing the following:
* Filled a null value with the average value of the column

After the data is clean, I engineer the features by doing the following:
* Subtracted the year 2014 with the year_birth column to get the age of the customer
* Grouped the age column then made a new column named generation
* Sum up all the products bought
* Sum up all the purchases made
* Sum up all the children the customer have
* Transformed the education level values to either 'Undergraduate' or 'Postgraduate'
* Transformed the marital status values to either 'In Relationship' or 'Single'
* Sum up all the family members the customer have
* Sum up all the marketing campaigns the customer accepted
* Transformed Dt_Customer by converting the data type from string to datetime 
* Made a new column named Date_Collected based on the assumption that the last time the data was updated was December 7, 2014 
* Made a new column named Customer_Enrolled based on subtraction between Date_Collected with Dt_Customer to get the total days of the customer's enrollment in the company
* Made a new column named Days_Active based on subtraction between Customer_Enrolled with Recency to get the days when the customer was actively interacting with the company
* Dropped columns such as ID, Year_Birth, Kidhome, Teenhome, Dt_Customer, Z_CostContact, Z_Revenue, Date_Collected, Customer_Enrolled to reduce the dimensionality of the dataset
* Removed Outliers

# Exploratory Data Analysis
After I cleaned and engineered the data, I analyze the data so I could get an insight out of it.

Below are a few highlights from my analysis.

![Income_Edu](https://user-images.githubusercontent.com/60106788/141610484-aa690f46-c117-4bf4-a672-b5f9ec8abc62.PNG)
![Mnt_Prods](https://user-images.githubusercontent.com/60106788/141610486-2fa99f01-d3b2-40ee-a3cb-a6a6c5c3a090.PNG)
![cust_gen](https://user-images.githubusercontent.com/60106788/141610499-b2f9ebdb-d395-4ebc-ab10-35e6949eeb47.PNG)
![corr_income_purchase](https://user-images.githubusercontent.com/60106788/141610482-4eeeaa60-87bc-4b7c-809a-41ffa5ac474a.PNG)
![corr_each_columns](https://user-images.githubusercontent.com/60106788/141610481-52633133-7a0a-4edd-8d17-3f73438fb216.PNG)

# Model Building 
First, I manually encoded Education and Marital Status then scale the essential features for modelling. After that I put the scaled features into a new variable named X.

I utilized the Elbow Method to pick the best K value for K-Means

![elbow_method](https://user-images.githubusercontent.com/60106788/141610843-712e4fea-2e9b-491e-b6f5-51f90d715a03.PNG)

I picked 4 because it's the best K value for K-Means. After the modelling process is done, I assigned each clusters to every row in the dataset by making a new column named Cluster.

# Model Performance
From the results of the clustering analysis, there are four types of customer:

1. 48% of customers (Majority)
* All of them are Postgraduates
* Higher number of customers who are in relationship than single customers
* Have an approximately 20k-50k of income
* Around 25 to 60 years old with the maximum around 35 to 45 years old
* Bought approximately 50-400 products
* Made a purchase approximately 5-20 times
* Higher number of children than no child
* Most of them reject the marketing campaign
* Highest number of customers who have loyalty with the company for a long period of time

2. 38% of customers
* Slightly lower number of Postgraduates than 48% of customers
* It's the same circumstances as 48% of customers but slightly lower number of customers
* Have an approximately 40k-80k of income
* Around 30 to 70 years old with the maximum around 45 to 60 years old
* Bought approximately 500-1700 products
* Made a purchase approximately 15-30 times
* Slightly higher number of children than no child
* Most of them reject the marketing campaign
* Slightly lower number of loyal customers compared to 48% of customers

3. 12% of customers 
* Significantly lower Postgraduates than the 38% of customers 
* The number of customers who are in relationship are slightly higher than single customers
* Have an approximately 70k-90k of income
* Around 20 to 70 years old with the maximum around 30 to 60 years old
* Bought approximately 800-2000 products
* Made a purchase approximately 15-25 times
* Higher number of no child than have children
* None of them reject the marketing campaign
* Significantly lower number of loyal customers compared to 38% of customers

4. 2% of customers (Minority)
* All of them are Undergraduates
* It's the same circumstances as 12% of customers but with lower number
* Have an approximately 15k-30k of income
* Around 20 to 65 years old with the maximum around 35 to 40 years old
* Bought approximately 20-100 products
* Made a purchase approximately 5-10 times
* Slightly higher number of children than no child
* Most of them reject the marketing campaign
* Least number of loyal customers









