
<h1 align="center">Insights to the Marketing team in Food and Beverage industry</h1>


### Introduction 
CodeX is a German beverage company that is aiming to make its mark in the Indian market. A few months ago, they launched their energy drink in 10 cities in India.Their Marketing team is responsible for increasing brand awareness, market share, and product development. They conducted a survey in those 10 cities and received results from 10k respondents. 

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Project Overview
This dashboard will enable the marketing team to convert survey results to meaningful insights which the team can use to drive actions.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Data Sources
The dataset contains 3 csv files:
1. dim_cities
2. dim_respondents
3. fact_survey_responses
   
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Tools
- SQL
- PowerBI -Data Cleaning, Data Visualization and creating dashboards
- MS Powerpoint - powerpoint presentation

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Data Cleaning/Preparation
- Column names renamed.  
- Checked datatype of each column and changed it if there is any mismatch.  
- Rows having errors and empty values were checked and removed.


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Data Modelling
**dim_respondents and fact_survey_responses**:  
- dim_respondents has a primary key respondent_ID.  
- fact_survey_responses contains a unique respondent_id which serves as a foreign key.  
**Since fact_survey_responses contains a unique respondent_id, there is a one-to-one relationship between dim_respondents and fact_survey_responses.** 

**dim_respondents and dim_cities:**
- dim_respondents has a foreign key city_ID referring to dim_cities.  
- dim_cities has a primary key city_ID.  
**Each respondent can belong to one city, but a city can have multiple respondents. This establishes a many-to-one relationship between dim_respondents and dim_cities.**    

**Summary of Cardinality:**    
- dim_respondents to fact_survey_responses: One-to-One  
- dim_respondents to dim_cities: Many-to-One    

![image](https://github.com/user-attachments/assets/6e37fc04-6133-4e79-abf8-99ec80174656)



----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Following Calculated Columns, Measures and tables were created
 - **Calculated columns added in Sales table**
   1) **HealthConcernFlag**
  
     ![image](https://github.com/user-attachments/assets/93fc1fca-8ac6-4866-a9e2-861c47ff5e6e)

      
       
 - **Measures created in Sales table**
   1) Avg Taste experience   
      ```Avg Taste experience = AVERAGE(fact_survey_responses[Taste_experience])```
      
   2) Count of Consumer frequency    
      ```Count of Consumer frequency = COUNT(fact_survey_responses[Consume_frequency])```  
      
   3) Count of consumption situation    
      ```Count of consumption situation = COUNT(fact_survey_responses[Typical_consumption_situations])```
      
   4) Count of each Brand  
      ```Count of each Brand = COUNT(fact_survey_responses[Current_brands])```
      
   5) Improvements_desired  
      ```Improvements_desired = count(fact_survey_responses[Improvements_desired])```
      
   6) PercentageOfHealthConcern
      
      ![image](https://github.com/user-attachments/assets/dea2ce0e-9941-4b80-9fbd-f509020c2419)

      
   7) PercentageOfNoHealthConcern  

       ![image](https://github.com/user-attachments/assets/15914d44-5615-45fe-be84-1451e4103ec8)

   8) Top_Brand

        ![image](https://github.com/user-attachments/assets/fbc4f69e-1870-459f-a018-585a42abc0b2)

    
   9) Total No of Cities   
       ```Total No of Cities = DISTINCTCOUNT(dim_cities[City])```

   10) Total No of Females  

        ![image](https://github.com/user-attachments/assets/d78e3022-f864-4ce3-ad21-f6b322a92541)

   11) Total Respondents   
        ```Total Respondents = DISTINCTCOUNT(dim_repondents[Respondent_ID])```


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Exploratory Data Analysis

I have added 3 important pages.  
1) Sales performance tracking
2) Vendor performance analysis
3) Manager level analysis  

Additional information will be available in Top 10 vendor, Manager and vendor info pages.  

**Sales Performance**   
a) In sales performance report page, 4 cards were inserted to show Total sales, Total quantity sold, Average sales amount and Total orders.  
b) A **line chart** with total sales over Order month shown in the left of the report.  
c) Two Period selector slicer has been created. One for showing **14 days Moving average and latest 3 months sales over order date** (line plot)  
d) Second Period selector slicer helps to view the **last 7, 14 and 28 days sales amount**  (line plot)  
e) Page navigator icons (buttons with image) added at the left of the report page to help for navigation to other pages  

**Vendor Performance**    
a) In Vendor performance report page, total no. of vendors card was added along with other cards.   
b) Two **slicers** were added: Vendor and Manager. To choose vendor or manager based on the need.  
c) **Pie chart** added to display the top 10 vendors based on the sales.  
d) **Horizontal bar chart** added to display the total quantity sold by each vendor with the vendor having maximum sales in the top.  
e) Total orders by order month have been shown as **vertical bar chart** with the month having higher orders in the beginning and lower orders at the end.  
f) Vendors with second best selling item has been shown with the Item ID in a table visual  

**Manager level analysis**   
a) A **funnel chart** has been used to show total sales by manager  
b) Total number of managers in the company is shown as card visual on top of the report.  
c) **Tree map** shown to display the total quantity sold under each manager.  
d) Count of distinct items, sales amount, count of vendor name with respect to each manager has been listed in the form of **tabular visual**  
e) Table with manager on each row is provided with **drill through** option to see the details about the selected manager in the table of Manager report.



----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Results/ Findings
**Sales Trends**:  
- Total sales amount saw a significant increase in March, reaching its peak towards the end of the month. After this peak, sales began to gradually decline.    

**Top Vendors by Sales Amount**:  
- Onus Global Fulfillment: Contributed approximately 10% of the total sales amount.  
- Liola Home: Contributed approximately 7% of the total sales amount.  
- South Store: Contributed approximately 6.1% of the total sales amount.  

**Quantity Sold**:  
- The total quantity sold by Onus Global Fulfillment was 61,931 units, making up approximately 10% of the overall quantity sold. This was followed by OJCommerce, South Store, and Fulfillment Concepts in terms of quantity sold.

**Order Volume by Month**:   
- The highest number of orders was recorded in March, followed by April, May, and January.

**Total Sales by Manager**:  
Manager A: Highest sales amount of $41.81M, managing 179 vendors and 29,199 distinct items.  
Manager M: Total sales of 80.20K, managing 98 vendors and 7,770 distinct items.  
Manager J: Total sales of 2.10M, managing 29 vendors and 4,707 distinct items.  
Manager V: Total sales of 2.40M, managing 46 vendors and 4,571 distinct items.  
Manager N: Total sales of 153.04K, managing 61 vendors and 859 distinct items.  
Manager X: Total sales of 80.20K, managing 9 vendor and 294 distinct items.    

**Linear Trend Analysis**:  
There is a clear linear trend between the **count** of distinct **items**(item_id) and **total sales**, indicating that increasing the number of items significantly boosts total sales.
In contrast, the count of vendors does not exhibit a linear trend with total sales, suggesting that simply increasing the number of vendors does not lead to a significant rise in sales

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Recommendation  
1) **Focus on March Sales Peaks**:  
- Promotional Campaigns: Since March saw a significant increase in sales, consider running targeted promotional campaigns during this month to capitalize on the trend.  
- Stock Management: Ensure that inventory levels are adequate to meet the expected increase in demand in March.  

2) **Leverage Top Vendors**:  
- Partnership Development: Strengthen relationships with top vendors like Onus Global Fulfillment, Liola Home, and South Store to maintain and potentially increase their contribution to overall sales.  
- Vendor Incentives : Provide incentives or support to these vendors to encourage the introduction of new items or exclusive deals that could drive higher sales.  

3) **Optimize Product Offerings**:
- Expand Item Range: Since there is a linear trend between the count of distinct items and total sales, increasing the variety of items offered could lead to higher sales.
- Analyze Item Performance: Regularly review the performance of distinct items and focus on promoting high-performing items while reconsidering or discontinuing low-performing ones.

4) **Monthly Sales Analysis**:
- Seasonal Adjustments: Given the high order volumes in March, April, May, and January, plan for seasonal adjustments in inventory and marketing strategies to align with these peak months.  
- Continuous Monitoring: Use historical sales data to predict future trends and adjust sales strategies accordingly.    

5) **Enhance Vendor Management**:
- Vendor Count vs. Item Count: The findings indicate that simply increasing the number of vendors does not significantly impact sales. Focus on increasing the count of distinct items from each vendor instead.  
- Performance Benchmarks: Establish performance benchmarks for vendors based on sales, item count, and other relevant metrics to ensure consistent performance across the board.  

6) **Sales and Item Correlation**:
- Data-Driven Decisions: Utilize the clear correlation between item count and sales to make data-driven decisions on inventory management and product offerings.    
- Predictive Analytics: Implement predictive analytics tools to forecast the impact of adding new items on overall sales and adjust strategies accordingly.    

**Example Action Plan**  
-  March Promotions: Launch a "Spring Sale" campaign every March, featuring discounts and special offers on popular items.  
-  Vendor Partnerships: Schedule quarterly meetings with top vendors to discuss performance, introduce new products, and negotiate better terms.  
-  Inventory Expansion: Conduct market research to identify new product categories that could be introduced to increase item variety and boost sales.  
-  Performance Dashboards: Develop and regularly update Power BI dashboards that provide real-time insights into vendor and item performance for the sales team.  
-  Training: Train the sales team on using data analytics tools to monitor performance and make informed decisions.    

By implementing these recommendations, the sales team at ABC eCommerce can effectively monitor and improve the performance of various vendors and items, ultimately driving higher sales and better customer satisfaction.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Dashboard 
- Check the dashboard here: https://mavenanalytics.io/project/17351
 

















