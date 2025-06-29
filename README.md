# Kultra-Mega-Stores-Inventory-Analysis

This capstone project presents a comprehensive analysis of Kultra Mega Stores Inventory sales business operations, leveraging data to uncover key trends, opportunities, and challenges. Through a series of business questions, we explore sales performance, customer behavior, shipping efficiency, and more, providing actionable insights to inform strategic decision-making.


## 🔍 Objective
To extract and communicate key insights from the sales dataset for strategic decision-making by KMS management.

## 💾 Tools Used
- SQL Server 
- GitHub for project documentation and presentation

## 🧠 Key Questions Answered and SQl Queries

1. Which product category had the highest sales?

``` SQL 
SELECT Product_Category, SUM(Sales) AS TotalSales
FROM KMS
GROUP BY Product_Category
ORDER BY TotalSales DESC;
```
2. What are the top and bottom-performing regions?

-- Top 3

``` SQL 
SELECT TOP 3 Region, SUM(Sales) AS TotalSales
FROM KMS
GROUP BY Region
ORDER BY TotalSales DESC;

```

-- Bottom 3

``` SQL 
SELECT TOP 3 Region, SUM(Sales) AS TotalSales
FROM KMS
GROUP BY Region
ORDER BY TotalSales ASC;
```

3. What were the total appliance sales in Ontario?

``` SQL 

SELECT SUM(Sales) AS TotalApplianceSale
FROM KMS
WHERE Product_Sub_Category = 'Appliances' AND Region = 'Ontario';
```
4. How can revenue be increased from the bottom 10 customers?

``` SQL
 
SELECT TOP 10 Customer_Name, SUM(Sales) AS TotalSales
FROM KMS
GROUP BY Customer_Name
ORDER BY TotalSales ASC;
```
5. Which shipping method incurred the highest cost?

``` SQL
SELECT TOP 1 Ship_Mode, SUM(Shipping_Cost) AS TotalShippingCost
FROM KMS
GROUP BY Ship_Mode
ORDER BY TotalShippingCost DESC;
```
6. Who are the most valuable customers and what do they buy?

``` SQL 
SELECT TOP 10 Customer_Name, SUM(Sales) AS TotalSales, COUNT(DISTINCT Product_Name) AS UniqueProducts
FROM KMS
GROUP BY Customer_Name
ORDER BY TotalSales DESC;

```

7. Which small business customer had the highest sales?

``` SQL 

SELECT TOP 1 Customer_Name, SUM(Sales) AS TotalSales
FROM KMS
WHERE Customer_Segment = 'Small Business'
GROUP BY Customer_Name
ORDER BY TotalSales DESC;
```
8. Which corporate customer placed the most orders (2009–2012)?

``` SQL 

SELECT TOP 1 Customer_Name, COUNT(DISTINCT Order_ID) AS OrderCount
FROM KMS
WHERE Customer_Segment = 'Corporate'
GROUP BY Customer_Name
ORDER BY OrderCount DESC;

```
9. Who is the most profitable consumer customer?

```  SQL 

SELECT TOP 1 Customer_Name, SUM(Profit) AS TotalProfit
FROM KMS
WHERE Customer_Segment = 'Consumer'
GROUP BY Customer_Name
ORDER BY TotalProfit DESC;

```
10. Which customers returned products and their segment?

``` SQL 

SELECT DISTINCT Customer_Name, Customer_Segment, Return_Status
FROM VW_KMSOrderStatus_tbl
WHERE Return_Status = 'Returned';

```

## 📈 Summary of Key Insights
|Insight|Summary|
|-------|-------|
|Top-Selling Product Category|Technology led with $5.98M in sales.|
|Top Region|West Region led with $3.6M in total sales.|
|Lowest Performing Region|Nunavut had the least sales ($116K).|
|Appliance Sales in Ontario|$202K total sales.|
|Most Expensive Shipping Method|Delivery Truck ($51.9K).|
|Most Valuable Customer|Emily Phan with $117K+ in sales, primarily in Technology.|
|Most Orders by a Corporate Customer (2009–2012)|Adam Hart (18 orders).|
|Top Small Business Customer|Dennis Kane ($75.9K in sales).|
|Most Profitable Consumer|Emily Phan ($34K in profit).|
|Returned Orders|419 returned orders, across all customer segments.|


## 📌 Recommendations

- *Focus on Top Product & Regions:* Leverage the performance of Technology and expand in the West and Ontario.

- *Target Bottom 10 Customers:* Engage them with personalized promotions or loyalty incentives.

- *Optimize Delivery Truck Costs:* Explore shipping partnerships or negotiate better rates.

- *Reward Loyal High-Spending Customers:* Offer exclusive discounts to top customers like Emily Phan and Deborah Brumfield.

- *Analyze Product Returns:* Investigate root causes in returned products per segment and reduce return rates.



## 👨‍💻  About Me
**[Oluwayemisi Aba]**  
Data Analyst | SQL | Excel | Power BI  


