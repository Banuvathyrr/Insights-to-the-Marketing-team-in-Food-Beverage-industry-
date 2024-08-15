
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

I have added 5 important pages.  
1) Demographic insights  
2) Consumer Preference
3) Competition analysis
4) Brand penetration
5) Brand perception 



**Demographic insights**   
a) In Demographic report page, 4 cards were inserted to show Total respondents, Total number of cities, Total number of males and females.  
b) A **Bar chart** shows total respondents for each city.  
c) The **Pie chart** gives the percentage split of total respondents for each gender.  
d) Stacked area chart shows the distribution of respondent count with respect to age
e) Multi row card gives the count of total male and females in tier 1 and 2 cities

**Consumer Preference**    
a) In Consumer preference report page, % of respondents showing health concerns was shown with average taste experience as card  
b) **Bar chart** displays the count of conumer frequency   
c) **Horizontal bar chart** added to display the total respondents with respect to each marketing channel.    
d) Count of each brand was shown using a bar chart  
e) Typical consumption situation was shown using a funnel chart.  
f) Total respondents for each brand with thier consume reason has been shown in the form of a Matrix.  
  




----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Results/ Findings
**Demographic insights**
- In the Codex survey, a total of 10,000 respondents participated across 10 cities. The survey saw a higher number of male respondents compared to female respondents. The higher number of male respondents might reflect gender trends in the food and beverage industry workforce or areas of interest that are currently male-dominated, such as certain sectors of food production or regulation.    

- Bangalore's Leading Position: The high number of respondents from Bangalore suggests a strong interest in the food and beverage industry, possibly due to its diverse culinary scene and vibrant restaurant and hospitality sector. Bangalore is known for its tech-savvy population, which may be more engaged in health, nutrition, and culinary trends.  

- Hyderabad and Mumbai: Both cities have rich culinary histories and thriving food and beverage industries. Hyderabad's famous cuisine and Mumbai's diverse food culture likely contribute to their high engagement levels in the survey. These cities may also have a higher concentration of professionals in the food and beverage industry, influencing the survey's relevance.  

- Chennai and Pune: Chennai is known for its traditional South Indian cuisine, while Pune has a growing food scene, with an emphasis on innovation and diverse food offerings. The interest from these cities might reflect their dynamic food industries and consumer interest in new food and beverage trends.  

- Kolkata and Ahmedabad: Known for their distinct culinary traditions, these cities' participation might indicate an interest in how traditional foods are represented in the Codex standards or a growing curiosity about global food trends and safety regulations.  

- Delhi: As the capital with a rich and varied food culture, Delhi's lower respondent rate could suggest either market saturation with surveys or a need for more targeted engagement strategies in the food and beverage sector.  

- Jaipur and Lucknow: With strong culinary traditions, these cities may have lower engagement due to a lesser focus on international food standards or a need for more awareness and education on Codex guidelines in the food and beverage sector.

- Greater Awareness and Engagement: Tier 1 cities like Bangalore, Hyderabad, Mumbai, and Chennai typically have more access to information and media related to global food and beverage trends, including Codex standards. This increased awareness can lead to higher participation in relevant surveys.  

**Consumer Preference**
- High Frequency of 2-3 Times a Week: The most popular consumption pattern is drinking beverages 2-3 times a week. This suggests that consumers enjoy beverages regularly but may still view them as an occasional treat rather than a daily necessity. This frequency may indicate that beverages are often consumed socially or as a complement to meals.

- Online Ads Dominance: The highest number of respondents indicated exposure to marketing through online ads. This suggests that digital advertising is highly effective in reaching consumers, likely due to its widespread presence on social media platforms, search engines, and websites. Online ads offer precise targeting and personalization, making them a powerful tool for engaging specific audience segments.

- Coca-Cola and Pepsi's leading positions highlight the importance of maintaining strong brand loyalty through consistent marketing and engagement with consumers. These brands should continue to innovate while preserving their core identities.  

- Codex and Sky 9 should focus on building brand recognition and expanding their market presence through unique value propositions and effective distribution strategies.
    

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
 

















