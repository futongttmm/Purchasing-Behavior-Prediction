# Purchasing Behavior Prediction

**Explore the data and gain some insights.  Build classification and regression models to predict customer purchasing behavior.**

## About the data

In 1998, the Adventure Works Cycles company collected a large volume of data about their existing customers, including demographic features and information about purchases they have made. The company is particularly interested in analyzing customer data to determine any apparent relationships between demographic features known about the customers and the likelihood of a customer purchasing a bike. 
Additionally, the analysis should endeavor to determine whether a customer's average monthly spend with the company can be predicted from known customer characteristics.

This data consists of three files, containing data that was collected on January 1st 1998.

**AdvWorksCusts.csv**   
Customer demographic data consisting of the following fields:

- CustomerID (integer): A unique customer identifier.
- Title (string): The customer's formal title (Mr, Mrs, Ms, Miss Dr, etc.)
- FirstName (string): The customer's first name. 
- MiddleName (string): The customer's middle name.
- LastName (string): The customer's last name.
- Suffix (string): A suffix for the customer name (Jr, Sr, etc.)
- AddressLine1 (string): The first line of the customer's home address.
- AddressLine2 (string): The second line of the customer's home address.
- City (string): The city where the customer lives.
- StateProvince (string): The state or province where the customer lives.
- CountryRegion (string): The country or region where the customer lives.
- PostalCode (string): The postal code for the customer's address.
- PhoneNumber (string): The customer's telephone number.
- BirthDate (date): The customer's date of birth in the format YYYY-MM-DD.
- Education (string): The maximum level of education achieved by the customer: Partial High School, High School, Partial College, Bachelors, Graduate Degree
- Occupation (string): The type of job in which the customer is employed: Manual, Skilled Manual, Clerical, Management, Professional
- Gender (string): The customer's gender (for example, M for male, F for female, etc.)
- MaritalStatus (string): Whether the customer is married (M) or single (S).
- HomeOwnerFlag (integer): A Boolean flag indicating whether the customer owns their own home (1) or not (0).
- NumberCarsOwned (integer): The number of cars owned by the customer.
- NumberChildrenAtHome (integer): The number of children the customer has who live at home.
- TotalChildren (integer): The total number of children the customer has.
- YearlyIncome (decimal): The annual income of the customer.

**AW_AveMonthSpend.csv**   
Sales data for existing customers, consisting of the following fields:
- CustomerID (integer): The unique identifier for the customer.
- AveMonthSpend (decimal): The amount of money the customer spends with Adventure Works Cycles on average each month.

**AW_BikeBuyer.csv**   
Sales data for existing customers, consisting of the following fields:
- CustomerID (integer): The unique identifier for the customer.
- BikeBuyer (integer): A Boolean flag indicating whether a customer has previously purchased a bike (1) or not (0).


## Data Preparation and Data Exploration
**[DataPreparation.ipynb](https://gitlab.com/TTMM__/purchasing-behavior-prediction/-/blob/master/DataPreparation.ipynb)**   

Clean the data by replacing any missing values and removing duplicate rows. Here, the missing values are coded by NaN (np.nan).
In this dataset, each customer is identified by a unique customer ID. 
The file without duplicated records is retained in 
*[PreparedData\AdvWorksCusts_Prepared.csv](https://gitlab.com/TTMM__/purchasing-behavior-prediction/-/blob/master/PreparedData/AdvWorksCusts_Prepared.csv), 
[PreparedData\AW_AveMonthSpend_Prepared.csv](https://gitlab.com/TTMM__/purchasing-behavior-prediction/-/blob/master/PreparedData/AW_AveMonthSpend_Prepared.csv), 
[PreparedData\AW_BikeBuyer_Prepared.csv](https://gitlab.com/TTMM__/purchasing-behavior-prediction/-/blob/master/PreparedData/AW_BikeBuyer_Prepared.csv)*.

Prepare the training and testing features and labels by converting categorical variables into one-hot vectors and numeric variables into scaling values, 
and store the array for features and labels as
*[PreparedData\BikeBuyerFeatures.csv](https://gitlab.com/TTMM__/purchasing-behavior-prediction/-/blob/master/PreparedData/BikeBuyerFeatures.csv), 
[PreparedData\BikeBuyerLabels.csv](https://gitlab.com/TTMM__/purchasing-behavior-prediction/-/blob/master/PreparedData/BikeBuyerLabels.csv), 
[PreparedData\AveMonthSpendFeatures.csv](https://gitlab.com/TTMM__/purchasing-behavior-prediction/-/blob/master/PreparedData/AveMonthSpendFeatures.csv), 
[PreparedData\AveMonthSpendLabels.csv](https://gitlab.com/TTMM__/purchasing-behavior-prediction/-/blob/master/PreparedData/AveMonthSpendLabels.csv)*.

**[DataExploration.ipynb](https://gitlab.com/TTMM__/purchasing-behavior-prediction/-/blob/master/ModelImprovment/DataExploration.ipynb)**

Explore the data by calculating summary and descriptive statistics for the features in the dataset, 
calculating correlations between features, and creating data visualizations to determine apparent relationships in the data.


## Classification for Predicting Potential Customers
**[BikeBuyerPrediction.ipynb](https://gitlab.com/TTMM__/purchasing-behavior-prediction/-/blob/master/BikeBuyerPrediction.ipynb)**

1. Use the Adventure Works Cycles customer data you worked with in to create a classification model that predicts whether or not a customer will purchase a bike. 
2. The model predicts bike purchasing for new customers for whom no information about average monthly spend or previous bike purchases is available.
3. Apply the information of the data learned from data exploration to building, testing, and optimizing a predictive machine learning model 
(eg. logistic regression classifier, random forest classification, multi-layer perceptron classifier, Adaboost classifier, SVM).
4. Use model improvement method to improve model performance (eg. feature selection, dimensionality reduction).

## Regression for Estimate Average Monthly Spend of New Customers

**[AveMonthSpendPrediction.ipynb](https://gitlab.com/TTMM__/purchasing-behavior-prediction/-/blob/master/AveMonthSpendPrediction.ipynb)**

1. Use the Adventure Works Cycles customer data you worked with in to create a regression model that predicts a customer's average monthly spend. 
2. The model predicts average monthly spend for new customers for whom no information about average monthly spend or previous bike purchases is available.
3. Apply the information of the data learned from data exploration to building, testing, and optimizing a predictive machine learning model 
(eg. linear regression, random forest, multi-layer perceptron, gradient boost).
