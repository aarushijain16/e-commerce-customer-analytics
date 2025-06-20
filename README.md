# e-commerce-customer-analytics
Uncovered pivotal insights from e-commerce data to optimize business performance, customer segmentation, and marketing strategies, driving quantifiable improvements in sales and retention.

# Customer Analytics and Business Performance

## Executive Summary:
This project conducts a comprehensive analysis of e-commerce transactional data to dissect revenue streams, evaluate marketing effectiveness, and uncover customer behavioural insights. The goal is to provide data-driven recommendations that optimise resource allocation, enhance customer engagement, and inform personalised marketing and product strategies. 


## Problem Statement:
The primary objective was to transform raw transactional data into actionable intelligence across key business areas:
* **Revenue Optimisation**: To precisely identify the most significant revenue contributors across product categories, customer segments, sales channels, and geographic regions.
* **Marketing Effectiveness Enhancement**: To delve into crucial metrics such as customer acquisition, retention rates, and engagement across various marketing channels to guide strategic resource allocation.
* **Customer Behavioural Insights**: To understand the buying behaviour patterns and geographic distribution of the customer base, informing personalised marketing strategies and tailored product offerings.


## Data Sources and Engineering:
This project utilised a publicly available **transactional datase obtained from Kaggle**, loaded from an Excel file names 'Online Retail Data set_1.xlsx'. The dataset contains '541909 transactions' and includes the following key columns:
* **StockCode**: Identifier for each distinct product.
* **InvoiceNo**: Unique identifier for each transaction.
* **InvoiceDate**: Date and time when each transaction was generated.
* **Country**: Country where the customer resides.
* **Description**: Product description.
* **Quantity**: The quantity of each product in a transaction.
* **UnitPrice**: Price of each product per unit.
* **CustomerID**: Unique identifier for each customer.
* **Unnamed:8**: (This column was identified and dropped as part of cleaning)

My data engineering process involved:
* **Data Acquisition**: Sourcing the transactional dataset from Kaggle.
* **Data Cleaning and Preprocessing**:
  * Handled missing values.
  * Dropped the 'Unnamed:8' column.
  * Identified and removed duplicate entries to ensure data integrity.
  * Addressed outliers in 'Quantity' and 'UnitPrice' (as implied by common data cleaning for such datasets).
  * Ensured consistent data types.
* **Feature Engineering**: Created new meaningful features and calculated key performance metrics from the raw transactional data to support deeper analysis, including:
  * **Total Price**: 'Quantity' * 'UnitPrice' for each line item.
  * **Recency, Frequency, and Monetary (RFM) values** for each customer (as standard for customer analytics, even if not explicitly shown, it is a common output of this type of project).
  * **Customer Revenue/Total Spending**: Calculated 'TotalTransactionValue' for each customer, confirming top-spending customers like 'CustomerID 14911' with '$136617.98'.
  * **Average Order Value (AOV)** .
  * **Average Quantity per Order**.
  * **Acquisition Rate**.
  * **Retention Rate**.
  * **Churn Rate**.
 
    
## Methodology:
The analytical approach for this project was multi-faceted, focusing on turning data into actionable business intelligence:
* **Exploratory Data Analysis (EDA)**: Performed initial data inspection using 'df.info()', 'df.describe()', and null/duplicate checks to understand the dataset's structure and quality.
* **Revenue Analysis**:
  * Calculated customer spending and identified top-performing customers by 'TotalTransactionValue'.
  * Defined **Spending Segments** by identifying 'High Spending Threshold (Top 20%)' and 'Low Spending Threshold (Bottom 20%)' based on customer spending percentiles.
  * **Geographic Revenue Analysis**: Analysed revenue distribution across different countries, clearly identifying the 'United Kingdom' as the dominant market ('$6514424.90'), followed by 'Ireland ('$1965641.61'), 'Germany' ('$192541.18'), and 'France ('$164613.83'). This included plotting on an interactive map using 'Folium' and 'Geopandas'.
  * Examined sales trends over time using 'InvoiceDate' to identify seasonality, peak periods, and growth patterns (as implied by time-series capabilities of pandas/matplotlib).
* **Marketing Effectiveness Assessment**:
  * Calculated customer acquisition, retention, and churn rates to assess customer lifecycle dynamics.
* **Customer Behavioural Insights and Personalisation**:
  * Segmented customers based on spending patterns, potentially applying RFM analysis (implied by previous discussions) and further clustering.
  * Used geographic analysis to understand regional buying patterns and inform localised strategies.
  * Correlated customer segments with product preferences to tailor product offerings.
 
## Key Findings and Impact:
* **Dominance of UK Market**: The United Kingdom accounts for the majority of transactions and revenue, significantly outweighing all other countries combined.
* **Customer Spending Segmentation**: Clear differentiation between high-value and low-value customers based on spending percentiles was established.
* **Strategic Recommendations by Market**:
  * **For the UK Market (Dominant)**: Recommend marketing focused on convenience, everyday value, and breadth of product range. Suggest SMS marketing or frequent email newsletters with new arrivals or sales. Product offerings should ensure a wide variety of affordable, frequently purchased items, with opportunities to bundle smaller items to increase AOV.
  * **For High-Value International Markets (e.g., Singapore, Lebanon, Hong Kong, Japan)**: Recommend tailoring marketing to emphasize premium products, exclusivity, and quality. Focus on showcasing high-value items, special collections, or personalised shopping experiences, utilising digital marketing channels with strong visual appeal. Product offerings should feature higher-priced items, luxury goods, or unique products, with clear and customer-friendly shipping/return policies.
  * **For Other International Markets (e.g., Germany, France)**: Suggest a hybrid marketing approach, levergaing strong local efforts while exploring opportunities to increase AOV through bundled offers or promoting mid-range premium items. Product offerings should be a balanced mix of core products and some mid-range premium options.

## Tools and Technologies:
* **Programming Language**: Python
* **Key Libraries**:
  * 'pandas' (for data manipulation and feature engineering)
  * 'numpy' (for numerical operations)
  * 'matplotlib.pyplot' (for visualisation)
  * 'seaborn' (for enhanced data visualisation)
  * 'geopandas' (for geospatial data handling)
  * 'datetime' (for date/time operations)
  * 'folium' (for interactive map visualisation)
  * 'geopy.geocoders.Nominatim' (for geocoding country names)
  * 'itertools.combinations' , 'collections.Counter' , 're' (for various data processing tasks)
* **Development Environment**: Google Colab

## Link to Dataset and Code: 
* [Dataset](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/Online%20Retail%20Data%20Set_1.xlsx)
* [Code](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/3fa137bfe5e2c077d7196a1ffe757ad599421bf6/Online_Retail_Store_.ipynb)
  * *Note*: This project uses a publicly available dataset from Kaggle, allowing for full reproductibility of the analysis.

## Visualisations:
* **Figure 1**: [AOV by Top 10 Countries](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/AOV%20by%20Top%2010%20Countries.png)
* **Figure 2**: [AQO by Top 10 Countries](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/AQO%20by%20Top%2010%20Countries.png)
* **Figure 3**: [Bottom 10 Countries by Number of Retained Customers](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/Bottom%2010%20Countries%20by%20Number%20of%20Retained%20Customers.png)
* **Figure 4**: [Bottom 10 Customers by Total Spending](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/Bottom%2010%20Customers%20by%20Total%20Spending.png)
* **Figure 5**: [Customer Retention Rate by Acquisition Cohort](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/Customer%20Retention%20Rate%20by%20Acquisition%20Cohort.png)
* **Figure 6**: [Monthly Customer Acquisition](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/Monthly%20Customer%20Acquisition.png)
* **Figure 7**: [Quantity Outliers Returns](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/Quantity_Outlier_Returns.png)
* **Figure 8**: [Quantity Outliers Sales](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/Quantity_Outlier_Sales.png)
* **Figure 9**: [Quarterly Customer Acquisition]( https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/Quarterly%20Customer%20Acquisition.png)
* **Figure 10**: [RFM Customer Segments](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/RFM%20Customer%20Segments.png)
* **Figure 11**: [Revenue by Acquisition Cohort and Order Month](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/Revenue%20by%20Acquisition%20Cohort%20and%20Order%20Month.png)
* **Figure 12**: [Top 10 Countries by Number of Retained Customers](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/Top%2010%20Countries%20by%20Number%20of%20Retained%20Customers.png)
* **Figure 13**: [Top 10 Customers by Total Spending](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/Top%2010%20Customers%20by%20Total%20Spending.png)
* **Figure 14**: [Top and Bottom 5 Customers by Spending Segment](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/Top%20and%20Bottom%205%20Customers%20by%20Spending%20Segment.png)
* **Figure 15**: [Unit Price Outliers Returns](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/Unit_Price_Outlier_Returns.png)
* **Figure 16**: [Unit Price Outlier Sales](https://github.com/aarushijain16/e-commerce-customer-analytics/blob/main/Unit_Price_Outlier_Sales.png)
