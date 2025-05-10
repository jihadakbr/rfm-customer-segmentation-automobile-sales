# Automobile Sales Customer Segmentation (RFM Analysis)
This dataset contains information about car sales transactions, including customer demographics, vehicle details, and sales data. It is ideal for analysis to understand customer buying behavior, sales trends, and market preferences.

Dataset Source: [Kaggle](https://www.kaggle.com/datasets/ddosad/auto-sales-data/data)

---

## Table of Contents

1. [Dataset Overview](#dataset-overview)
2. [Project Overview](#project-overview)
3. [Main Objective](#main-objective)
4. [Specific Objectives](#specific-objectives)
5. [Data Understanding](#data-understanding)
6. [Data Preprocessing](#data-preprocessing)
7. [RFM Analysis & Results](#rfm-analysis--results)
   1. [Customer Segmentation](#customer-segmentation)
   2. [Key Insights](#key-insights)
      - [Customer & Transaction Overview](#customer--transaction-overview)
      - [Top Customer Segments by Sales](#top-customer-segments-by-sales)
      - [Product Category Performance](#product-category-performance)
      - [Deal Size Correlation](#deal-size-correlation)
      - [Sales & Customer Trends](#sales--customer-trends)
8. [Recommendations](#recommendations)
9. [Dashboard](#dashboard)
10. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
11. [Conclusion](#conclusion)
12. [License](#license)
13. [Contact](#contact)

---

## Dataset Overview

| Column Name               | Description                                                                                                      |
|---------------------------|------------------------------------------------------------------------------------------------------------------|
| **ORDERNUMBER**            | This column represents the unique identification number assigned to each order.                                 |
| **QUANTITYORDERED**        | It indicates the number of items ordered in each order.                                                         |
| **PRICEEACH**              | This column specifies the price of each item in the order.                                                      |
| **ORDERLINENUMBER**        | It represents the line number of each item within an order.                                                     |
| **SALES**                  | This column denotes the total sales amount for each order, which is calculated by multiplying the quantity ordered by the price of each item. |
| **ORDERDATE**              | It denotes the date on which the order was placed.                                                              |
| **DAYS_SINCE_LASTORDER**   | This column represents the number of days that have passed since the last order for each customer. It can be used to analyze customer purchasing patterns. |
| **STATUS**                 | It indicates the status of the order, such as "Shipped," "In Process," "Cancelled," "Disputed," "On Hold," or "Resolved." |
| **PRODUCTLINE**            | This column specifies the product line categories to which each item belongs.                                   |
| **MSRP**                   | It stands for Manufacturer's Suggested Retail Price and represents the suggested selling price for each item.    |
| **PRODUCTCODE**            | This column represents the unique code assigned to each product.                                                 |
| **CUSTOMERNAME**           | It denotes the name of the customer who placed the order.                                                       |
| **PHONE**                  | This column contains the contact phone number for the customer.                                                 |
| **ADDRESSLINE1**           | It represents the first line of the customer's address.                                                         |
| **CITY**                   | This column specifies the city where the customer is located.                                                   |
| **POSTALCODE**             | It denotes the postal code or ZIP code associated with the customer's address.                                  |
| **COUNTRY**                | This column indicates the country where the customer is located.                                                |
| **CONTACTLASTNAME**        | It represents the last name of the contact person associated with the customer.                                 |
| **CONTACTFIRSTNAME**       | This column denotes the first name of the contact person associated with the customer.                          |
| **DEALSIZE**               | It indicates the size of the deal or order, which are the categories "Small," "Medium," or "Large."             |

---

## Project Overview

Sales and customer engagement for an automobile company show fluctuating patterns, with significant peaks in November and December 2018 and 2019. These months are crucial for both sales and customer activity, but consistency remains a challenge. This project aims to address these challenges by performing an RFM (Recency, Frequency, Monetary) analysis on automobile sales data to segment customers and enhance marketing strategies.

---

## Main Objective

The goal of this project is to identify high-value clients by segmenting customers based on recency, frequency, and monetary values. Insights from this analysis will help improve customer retention, enhance marketing strategies, and boost overall sales.

---

## Specific Objectives

1. **Customer & Transaction Overview**: Analyze the total number of customers, transactions, sales, and average values for recency, frequency, and monetary metrics.
2. **Customer Segmentation**: Identify which customer segments contribute the most to total sales.
3. **Product Analysis**: Examine which product categories generate the highest sales and identify top-performing items within each segment.
4. **Deal Size Analysis**: Explore how deal size correlates with total sales.
5. **Sales Trends**: Identify trends in sales and customer activity over time.

---

## Data Understanding

The dataset, sourced from [Kaggle](https://www.kaggle.com/datasets/ddosad/auto-sales-data/data), focuses on automobile sales, covering transactions from 2018 to 2020. It includes customer demographics, transaction details, and product information.

- **Transactions**: 2,747 transaction records.
- **Columns**: 20 columns (includes order details, customer information, product categories).
- **Products**: Motorcycles, classic cars, vintage cars, trucks & buses, trains, ships, and planes.

---

## Data Preprocessing

1. **Removing Duplicates**: No duplicate data found.
2. **Handling Missing Values**: No missing data found.
3. **Data Type Conversion**: 
   - Converted `ORDERNUMBER` from string to integer.
   - Converted `ORDERDATE` from string to date format.
4. **Error Detection**: 
   - Formatted phone numbers.
   - Cleaned non-alphabetical characters.
5. **Profit Calculation**: 
   - Added a "Profit" column: `Profit = Sales – (Quantity Ordered * MSRP)`.
6. **Outlier Detection**: No extreme outliers found.
7. **RFM Transformation**: Created 9 customer segments based on RFM analysis.
8. **Exporting Data**: Saved cleaned data in CSV format for use in dashboards.

---

## RFM Analysis & Results

### Customer Segmentation
- **Recency, Frequency, and Monetary Scores**: Scores are calculated on a scale of 1 to 5 with defined thresholds.
- **9 Customer Segments**: From "Champions" to "At Risk", with detailed score intervals, descriptions, and actionable recommendations.

![rfm segmentation](https://raw.githubusercontent.com/jihadakbr/rfm-customer-segmentation-automobile-sales/refs/heads/main/img/rfm%20segmentation.png)

---

### Key Insights

![rfm metrics](https://raw.githubusercontent.com/jihadakbr/rfm-customer-segmentation-automobile-sales/refs/heads/main/img/rfm%20metrics.png)

1. **Customer & Transaction Overview**:
   - **89 customers**, **298 transactions**, **$9.76 million** total sales.
   - **Average Recency**: 180.61 days (moderate recency score).
   - **Average Frequency**: 3.35 purchases (moderate frequency).
   - **Average Monetary Value**: $110K per customer (high monetary value).

   **Insight**: Moderate recency and frequency scores indicate opportunities for customer reactivation and engagement, especially for high-value customers.

---

![sales and customer by segment](https://raw.githubusercontent.com/jihadakbr/rfm-customer-segmentation-automobile-sales/refs/heads/main/img/sales%20and%20customer%20by%20segment.png)

2. **Top Customer Segments by Sales**:
   - **Champions**: Contribute 38.4% of sales ($3.7M).
   - **At Risk**: Contribute 17.8% of sales ($1.74M), but need reactivation.
   - **Loyal Customers**: Contribute 17.3% of sales ($1.69M).
   - Other segments (e.g., Value Seekers, Casual Shoppers) contribute minimally.

---

![sales by product and segment](https://raw.githubusercontent.com/jihadakbr/rfm-customer-segmentation-automobile-sales/refs/heads/main/img/sales%20by%20product%20and%20segment.png)

3. **Product Category Performance**:
   - **Classic Cars**: Lead with $3.84M in sales.
   - **Vintage Cars**: $1.81M in sales.
   - **Trucks & Buses**: $1.11M in sales.
   - **Top-Performing Items**: Champions dominate all product categories.

---

![relationship between deal size and average sales](https://raw.githubusercontent.com/jihadakbr/rfm-customer-segmentation-automobile-sales/refs/heads/main/img/relationship%20between%20deal%20size%20and%20average%20sales.png)

4. **Deal Size Correlation**:
   - Larger deals significantly correlate with higher total sales.
   - **Large Deals**: $8,283 on average.
   - **Medium Deals**: $4,397 on average.
   - **Small Deals**: $2,063 on average.

---

![sales and customer trends](https://github.com/jihadakbr/rfm-customer-segmentation-automobile-sales/blob/main/img/sales%20and%20customer%20trends.png)

5. **Sales & Customer Trends**:
   - **Sales Peaks**: November and December 2018-2019 show seasonal spikes.
   - **Customer Trends**: Strong engagement during these months, driven by specific events or campaigns.

---

## Recommendations

1. **Boost Customer Retention**: Focus on customers with moderate recency and frequency scores. Implement loyalty programs and personalized promotions to encourage repeat purchases.
2. **Prioritize High-Value Segments**: Direct marketing efforts to "Champions" and "At Risk" segments. Offer VIP incentives and tailored promotions to retain these high-contributing customers.
3. **Encourage Larger Deals**: Offer volume discounts and bulk purchase incentives to increase the size of deals and total sales.
4. **Capitalize on Seasonal Peaks**: Plan marketing campaigns around November and December to maximize sales during these high-activity periods.

---

## Dashboard

A dashboard has been created to allow stakeholders to monitor customer segments and track performance metrics over time.

![RFM Analysis Dashboard](https://raw.githubusercontent.com/jihadakbr/rfm-customer-segmentation-automobile-sales/refs/heads/main/img/RFM%20Analysis%20Dashboard.png)

---

## Exploratory Data Analysis (EDA)

Performed using Jupyter Notebooks, including:

- **Skewness Transformation**: Ensured data normalization for accurate analysis.
- **Pairplot**: Visualized relationships between key variables.
- **Correlation Matrix**: Analyzed correlations between product categories, sales, and customer attributes.

---

## Conclusion

This project provides valuable insights into customer behavior and sales trends, empowering marketing teams to make data-driven decisions to boost engagement, optimize retention, and drive revenue growth.

---

## License

This project is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License](LICENSE).

![CC BY-SA 4.0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/by-sa.svg)

---

# Contact
For questions or collaborations, feel free to reach out:

- Email: [jihadakbr@gmail.com](mailto:jihadakbr@gmail.com)
- LinkedIn: [linkedin.com/in/jihadakbr](https://www.linkedin.com/in/jihadakbr)
- Portfolio: [jihadakbr.github.io](https://jihadakbr.github.io/)
