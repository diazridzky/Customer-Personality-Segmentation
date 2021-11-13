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
After importing the data, I needed to clean it up then made the following changes:
* Filled a null value with the average value of the column
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
* Made a new column named Customer_Enrolled based on subtraction between Date_Collected with Dt_Customer 
* Made a new column named Days_Active based on subtraction between Customer_Enrolled with Recency 
* Dropped columns such as ID, Year_Birth, Kidhome, Teenhome, Dt_Customer, Z_CostContact, Z_Revenue, Date_Collected, Customer_Enrolled to reduce the dimensionality of the dataset
* Removed Outliers

# Exploratory Data Analysis












