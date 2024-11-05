# LITA-Capstone-Project-2-Documentation

I am a data analyst in training with LADIES IN TECH AFRICA INCUBATOR HUB, where I am currently developing expertise in data manipulation, data analysis, and data visualization. This engaging experience is deepening my understanding of data-driven decision-making, enabling me to uncover significant patterns and insights through practical, project-based learning.

### Title of Project: Customer Segmentation for a Subscription Service

[Project Overview](#project-overview)

[Project Objectives](#project-objectives)

[Data Sources](#data-sources)

[Key Performance Metrics](#key-performance-metrics)

[Tools Used](#tools-used)

[Data Analysis](#data-analysis)

[Data Visualization](#data-visualization)

### Project Overview 
------
The project focuses on analyzing customer data for a subscription service to uncover key segments and trends. The objective is to gain insights into customer behavior, track subscription types, and identify critical patterns in cancellations and renewals.

### Project Objectives
------

The objectives of this project were defined to accomplish the following analytical goals:

1.

### Excel:


- Analyze customer data using pivot tables to find subscription patterns.

- Calculate the average subscription duration and identify the most popular subscription types.

- Create any other interesting reports.

### Data Sources
------

The data sources consist of the following key elements:
1.	CustomerID:A unique identifier for each customer. This links orders to specific customers and helps in customer management.
2.	CustomerName: The name of the customer associated with the subscription.
3.	Region: Refers to the geographical location where the order was placed or where the product is to be delivered. This helps in understanding the distribution and sales patterns across different regions.
4.	SubscriptionType: The type of subscription plan the customer has chosen (e.g., Premium, Basic, Standard).
5.	SubscriptionStart: The date when the customer’s subscription started. This can be used for tracking how long a customer has been subscribed and for subscription lifecycle analysis.
6. SubscriptionEnd: The date when the current subscription will end. It helps in managing renewal processes or identifying when customers may need to renew or be up for cancellation.
7. Canceled: A status indicator, usually "Yes" or "No," showing whether the customer has canceled their subscription. This can be used to track Attrition or cancellation rate.
8. Revenue: The amount of money generated from each customer. This is key for revenue tracking, determining customer lifetime value (CLV), or understanding the financial impact of different customer segments.

### Key Performance Metrics
------

(i) Total Revenue: This is the total sales income generated from various regions.

(ii) SubscriptionStart:  This is the day when a customer's subscription becomes active, initiating access to the service and triggering the billing cycle.

(iv) Subscription Type: This refers to the different models or categories of subscriptions offered by businesses, which dictate how customers access products or services.

(v) SubscriptionEnd: This is the date when a customer's subscription period concludes, which can have significant implications for both the service provider and the customer.
### Used Tools
---------


### Microsoft Excel: [download here](https://www.microsoft.com/en-ng/)

- Pivot Tables: Used for summarizing data and deriving insights related to revenue per subscription tpe, revenue by region, and no. of ccustomers by subscription type.
- Formulas and Functions: Essential for calculating performance metrics, calculations, data analysis, and to automate tasks.
- Data Visualizations (Charts and Graphs): Employed to produce visual representations of trends, comparisons, and critical insights.

### Exploratory Data Analysis (EDA):
Exploratory Data Analysis (EDA) involves examining the data to address various questions, such as:
- What is average subscription duration.
- Identify the most popular subscription types.
- What is revenue per SubscriptionType?
- What is the total revenue by region
- Calculate total nno. of customers by SubscriptionType


### Data Aalysis
-------

- Activated the pivot table command
- Created a chart to visualize revennue per SubscriptionType, revenue by region and no. of customers by SubscriptionType.

2.
### SQL:

### Used Tools
---------


### My SQL: [download here](https://www.my-sql-enterprise.com/en-ng/)

Here I am required to Write queries to extract key insights based on the following questions.

- retrieve the total number of customers from each region.

- find the most popular subscription type by the number of customers.

- find customers who canceled their subscription within 6 months.

- calculate the average subscription duration for all customers.

- find customers with subscriptions longer than 12 months.

- calculate total revenue by subscription type.

- find the top 3 regions by subscription cancellations.

- find the total number of active and canceled subscriptions.

### Query 1. Write a query to retrieve the total number of customers from each region.
  
```SQL
   SELECT Region, COUNT(CustomerID) AS TotalCustomers

   FROM CustomerData$

   GROUP BY Region;
  ```

### Query 2. Write a query to find the most popular subscription type by the number of customers.

```
SELECT TOP 1 SubscriptionType, COUNT(CustomerID) AS CustomerCount

   FROM CustomerData$

   GROUP BY SubscriptionType

   ORDER BY CustomerCount DESC;
  ```

### Query 3. Write a query to find customers who canceled their subscription within 6 months.

```
  SELECT CustomerID, CustomerName, SubscriptionType, SubscriptionStart, SubscriptionEnd

   FROM CustomerData$

   WHERE DATEDIFF(month, SubscriptionStart, SubscriptionEnd) <= 6

     AND Canceled = 1;
   ```

### Query 4. Write a query to calculate the average subscription duration for all customers.

```
   SELECT AVG(DATEDIFF(month, SubscriptionStart, SubscriptionEnd)) AS AvgSubscriptionDuration

   FROM CustomerData$;
   ```

### Query 5. Write a query to Calculate monthly sales totals for the current year:

```
SELECT CustomerID, CustomerName, SubscriptionType, SubscriptionStart, SubscriptionEnd

   FROM CustomerData$

   WHERE DATEDIFF(month, SubscriptionStart, SubscriptionEnd) > 12;
```

### Query 6. Write a query to calculate total revenue by subscription type.

  ```
    SELECT SubscriptionType, SUM(Revenue) AS TotalRevenue

   FROM CustomerData$

   GROUP BY SubscriptionType;
```

### Query 7. Write a query to find the top 3 regions by subscription cancellations.

  ```
SELECT TOP 3 Region, COUNT(CustomerID) AS Cancellations

   FROM CustomerData$

   WHERE Canceled = 1

   GROUP BY Region

   ORDER BY Cancellations DESC;
   ```

### Query 8. Write a queryy to find the total number of active and canceled subscriptions.

```
  SELECT 

       SUM(CASE WHEN Canceled = 0 THEN 1 ELSE 0 END) AS ActiveSubscriptions,

       SUM(CASE WHEN Canceled = 1 THEN 1 ELSE 0 END) AS CanceledSubscriptions

   FROM CustomerData$;
  ```




### DATA VISUALIZATION
---------
### PIVOT TABLE SHOWING; 
- REVENUE PER SUBBSCRIPTION TYPE

- REVENUE BY REGION

- NO OF CUSTOMERS BY SUBSCRIPTION TYPE
