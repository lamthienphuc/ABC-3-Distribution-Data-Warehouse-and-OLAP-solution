# ABC-3-Distribution-Data-Warehouse-and-OLAP-solution
Develop a well-structured relational schema for a data warehouse that effectively stores and manages the data provided by the ABC-3 Distribution company, Implement a multidimensional OLAP cube, Generate insightful reports
# Data Warehouse Design
Key Concepts for Data Warehousing:

● Dimensional Modeling: This is a data modeling technique specifically designed for data
warehouses. It focuses on organizing data around business processes and key business
dimensions.

● Measures: These are the quantitative values that being analyze (ResellerSales). They are
stored in the fact table. 

● Dimensions: These provide the context for the measures (e.g.,Date, Product,Reseller, Geography). They are stored in the dimension tables. 

● Granularity: This refers to the level of detail stored in the fact table. For example, sales
data can be stored at the daily, weekly, or monthly level.
# Star Schema
![image](https://github.com/user-attachments/assets/557bd7a0-cc40-47aa-9b07-b90b703aa594)
For this project focusing on reseller measures, the star schema is likely the most appropriate choice
due to its simplicity and efficiency for OLAP queries. It will have a central FactResellerSales table
containing sales metrics, and dimension tables like DimReseller, DimProduct, DimTime, DimGeography, and DimPromotion providing the context for those metrics.
# Cube Design for Reseller Measures
Measures are quantitative data stored in the cube, representing the information to be analyzed. In
the reseller context, typical measures include:
Reseller Sales Amount: Total sales revenue from resellers.
Order Quantity: Total number of products sold.
Product Cost: Total cost associated with products. 
Profit: The difference between revenue and cost.
These measures are aggregated across dimensions such as time, geography, and product categories.
![image](https://github.com/user-attachments/assets/494ecd25-e7d8-4a49-8710-8b717a0d2a7b)
# Dimensions
The dimensions used in the cube are:
Dim Date: Contains date-related attributes such as year, month, and day. 
Dim Sales Territory: Represents geographical sales areas, including country, region, and state. 
Dim Reseller: Stores reseller-specific information, including name, type, and location. 
Dim Product: Contains details about products, such as name, category, and subcategory. 
Dim Promotion: Includes promotional campaign details like promotion name, type, and start/end
dates. 
Dim Geography: Defines geographic locations with attributes like city, state, and country.
![image](https://github.com/user-attachments/assets/8becdb6c-60f8-42ab-a9db-cde1e0883bbc)
# Hierarchies
Hierarchies are logical structures within dimensions that allow data to be organized at different
levels of granularity. Examples include:
Time Hierarchy:
Calendar Year > Calendar Semester > Calendar Quarter > Calendar Month > Calendar Date.

![image](https://github.com/user-attachments/assets/7074f04b-b7fb-490f-91df-afbe106104fa)

Reseller Hierarchy:
Reseller Name > Geography Key > Business Type.

![image](https://github.com/user-attachments/assets/d4570a13-a62c-4b46-8583-68a5ecbd8ddc)

Promotion Hierarchy:
English Promotion Type > English Promotion Name.

![image](https://github.com/user-attachments/assets/2d183c8c-abfd-42a5-8c75-ef82ff06d74d)

Product Hierarchies:
All Products: Product Category Key > English Product Name. Product Line: Product Line > Model Name > Product Name.

![image](https://github.com/user-attachments/assets/cdbbf2a4-7f72-4622-9a41-6731b8c99cd4)

Geography Hierarchy:
Country-Region > State Province > City.

![image](https://github.com/user-attachments/assets/ee90b52c-ec34-4185-a439-717e682a4cb9)

Hierarchies enable efficient roll-up and drill-down operations, providing insights at various levels
of detail, which is crucial for decision-making processes.
# Report Generation and Analysis
![image](https://github.com/user-attachments/assets/87201532-3f23-4d0b-9224-f178cd90bfe8)
Insights and Findings
This dashboard displays distributor sales data and provides an overview of business performance. Below is a detailed analysis of each section
General Metrics:  
Total Order Quantity: 214,000 orders. This is the total number of orders placed through
distributors. 

Total Sales Amount: $80.45 million. This is the total sales value generated from distributor
orders.  

Average Tax: $6.44 million. This figure seems inaccurate as average tax is usually
represented as a percentage or a much smaller value compared to total sales. This may refer
to the total tax collected, rather than average tax.

Sales by Product Category:
Reseller Sales Amount by Product Subcategory: This bar chart shows that "Bikes" account
for the majority of sales ($66.30 million), followed by "Components" ($11.80 million), "Clothing" ($1.78 million), and "Accessories" ($0.57 million). 

Sales by Date and Product Category:Reseller Sales Amount by Date and Product Category: This line chart shows the sales trend
over time. Sales increased from around $0 million in 2010 to $18 million in 2011, $28
million in 2012, and $34 million in 2013. The steady growth in sales indicates positive
business performance.

Top 5 Countries by Sales: Top 5 Countries by Sales Amount: This table lists the top 5 countries contributing to sales
revenue, with the United States leading at $53.6 million, followed by Canada ($14.3
million), France ($4.6 million), the United Kingdom ($4.2 million), and Germany ($1.9
million). The total sales from these 5 countries amount to $80,450,596.98. 

Order Quantity by Category: Order Quantity by Category: This pie chart shows the percentage of orders by product
category: Bikes (34.99%), Components (22.87%), Clothing (30.09%), and Accessories
(12.05%). 

Order Quantity and Sales by Sales Territory and Date: Order Quantity and Sales Amount by Sales Territory Country and Date Key: This scatter
plot shows the relationship between order quantity and sales amount by country and date. It
provides detailed data for December 6, 2013. The value "Sales Amount - Fact Reseller Sales
33,574,834.16" may refer to the total sales for the selected date.
# Summary of Findings
The distributor sales analysis reveals strong overall performance with significant growth over time. Key findings include:  Strong Sales Growth: Total sales reached $80.45 million, with substantial year-over-year
increases from 2010 to 2013. 

Dominant Product Category: Bikes are the top-selling product category, generating
$66.30 million in sales, significantly outpacing Components, Clothing, and Accessories.

Key Geographic Markets: The United States is the largest market, contributing $53.6
million in sales, followed by Canada, France, the United Kingdom, and Germany. These
five countries account for the vast majority of total sales. 

Order Quantity Distribution: While Bikes lead in sales value, Clothing accounts for the
largest share of order quantity (30.09%), followed by Bikes (34.99%), Components
(22.87%), and Accessories (12.05%). This suggests varying average order values across
categories. 

Potential Data Inaccuracy: The reported "Average Tax" of $6.44 million seems unusually
high and likely represents total tax collected rather than average tax per order. 

Detailed Snapshot: A detailed analysis of December 6, 2013, provides a specific example
of the relationship between order quantity and sales amount within different sales territories. 

In summary, the business is experiencing healthy growth driven by bike sales in key markets like
the United States. Further analysis of the tax data and the relationship between order quantity and
sales value across different categories could provide additional insights.
# Recommendations
- Implement a Key Account Management Program for Top Resellers.
- Conduct a Regional Market Analysis for the Eastern Region.
- Re-evaluate the 'Summer Sale' Promotion Strategy.
- Develop a targeted training program for new resellers
