# Customer's Subscription Plans
## Content
- [Introduction](#introduction)
- [Data Description](#data-description)
- [Basic Statistics in the Dataset](#basic-statistics-in-the-dataset)
- [Methodology](#methodology)
- [Using Microsoft Excel for Analysis](#using-microsoft-excel-for-analysis)
- [Analysing with Sql](analysing-with-sql)
- [Power BI Analysis](#power-bi-analysis)
- [Data Analysis and Insight Generation](#data-analysis-and-insight-generation)
- [CONCLUSION](#conclusion)
### Introduction: 
 In today’s dynamic marketplace,it is crucial to have an understanding of customer subscription behaviour to enable Subscription-based businesses to foster long-term growth and strengthening customer commitment.Analyzing data like this creates a significant opportunity for businesses by utilizing data insights to refine marketing strategies and enhance customer experiences. This project investigates customer subscription plans to uncover patterns that impact cancellations and retention. The dataset consists of transaction records and associated information. By utilizing tools like: Excel , SQL( Structured Query Language) and Power BI. The dataset was carefully cleaned, analyzed, and visualized, providing a clearer perspective of the company's subscription dynamics and revealing opportunities for enhancement.
---------

### Data Description 
The dataset includes the following;
- Customer ID: Unique identifier for each transaction.
- Customer Name: This consists of the customer’s name.
- Subscription Type:Various types of subscription plans available for customers.
- Region: Different regions where customers subscribe to their plans.
- Subscription Start: The start date of customer’s subscription 
- Subscription End : End date of the customer’s subscription/Expiratory date.
- Cancelled : This shows customer's Cancellation and Retention.
- Revenue: The total sales or amount generated from each customer based on their choice of plan and duration.
------
### Basic Statistics in the Dataset
1. Total Revenue: #6.75Million
2. Total Number of Customers: 33,787
3. Average Revenue: #1,999
4. Subription duration: 365days
5. Number of Regions: 4

-------
### Methodology

Data Collection
The dataset for this analysis was provided by the Incubator Hub, an organization that supplies educational datasets for learning and training purposes. The data was provided in Excel format and was converted to Csv for analysis in Sql, making it easy for analysis.

Data Manipulation 
Checked for Spelling Errors, Duplicate Values, and Blank Cells: Ensured data quality by  removing duplicate entries, and blank cells.
Created a new column to show the duration of data plans.

### Using Microsoft Excel for Analysis
This tool was used to clean the dataset, remove duplicates and empty cells, it was also used to create Pivot Table to showcase insights geneated from the data,Excel was used to create a new column that calculate the duration of customer's data plan.
1.	Data Preparation
•	Data cleaning : Eliminated duplicated records to ensure Data Quality.


![Screenshot 2024-11-04 131317 pngduplicate values png2](https://github.com/user-attachments/assets/3feec180-3780-4f00-9e29-cf5fbc39ec74)

•	New columns calculated : Calculated the time between subscription start and subscription end date for each subscriber.

![extra column](https://github.com/user-attachments/assets/b52ede58-027a-4698-a2b7-f195213e005e)

3.	Subscription Statistics
   Displayed subscriber count, average subscription duration, average monthly revenue, and most popular subscription type.
4.	Customer Distribution and Segmentation
•	Subscription count by type : Created pivot tables to display counts for each subscription type 
•	Subscriber segmentation : Used pivot tables to display information of subscriber's activity (retained, canceled)

![pivot table 2](https://github.com/user-attachments/assets/f5beba56-5f79-46e6-9e03-2e8b0f34920d)

5. Created visualization of different key insights using Excel: Top performing subscription plan, Average sales,Total sales,Retained customers,Cancelled customers.
   
![EXCEL VISUAL 2](https://github.com/user-attachments/assets/21916655-fc32-4476-8c61-dc0c15364f28)

-------

### Analysing with Sql
The following key insights was queried;

1.	Total number of customers from each region.
2.	The most popular subscription type by the number of customers.
3.	Customers who canceled their subscription within 6 months.
4.	Average subscription duration for all customers.
5.  Customers with subscriptions longer than 12 months.
6.	Total revenue by subscription type.
7.	Top 3 regions by subscription cancellations.
8.	The total number of active and canceled subscriptions.

```sql
select * from [dbo].[LITAPROJECT 2 SQL]

-----------1.TOTAL NUMBER OF CUSTOMERS FOR EACH REGION--------------
select region, count(customerid) as Number_of_customer from [dbo].[LITAPROJECT 2 SQL]
group by region

-----------2.POPULAR SUBSCRIPTION TYPE BY THE NUMBER OF CUSTOMERS-----------
select subscriptiontype, count(customerid) as customers from [dbo].[LITAPROJECT 2 SQL]
group by subscriptiontype

---------3.CUSTOMERS WHO CANCELED THEIR SUBSCRIPTION WITHIN 6 MONTHS-------
select customerid from [dbo].[LITAPROJECT 2 SQL]
where datediff(month, subscriptionstart, subscriptionend)<= 6

---------4.AVERAGE SUBSCRIPTION DURATION FOR ALL CUSTOMERS---------------
select avg(datediff(day, subscriptionstart, subscriptionend)) as AVG_Duration from [dbo].[LITAPROJECT 2 SQL]
where subscriptionend is not null 

-----------5.CUSTOMERS WITH SUBSCRIPTIONS LONGER THAN 12 MONTHS--------
select customerid from [dbo].[LITAPROJECT 2 SQL]
where datediff(month, subscriptionstart, subscriptionend) > 12

------Change data type------
Alter Table [dbo].[LITAPROJECT 2 SQL]
Alter column [Revenue] money;

------------6.TOTAL REVENUE BY SUBSCRIPTION TYPE-------------
select subscriptiontype, sum(revenue) as total_revenue from [dbo].[LITAPROJECT 2 SQL]
group by subscriptiontype


--------------7.TOP 3 REGIONS BY SUBSCRIPTION CANCELLATIONS--------------
select region, count(*) as cancellations from [dbo].[LITAPROJECT 2 SQL]
where subscriptionend is not null
group by region
order by cancellations desc
offset 0 rows fetch next 3 rows only 

-------------8.TOTAL NUMBER OF ACTIVE AND CANCELED SUBSCRIPTION---------
select count(case when subscriptionend is null then 1 end) as active, 
count(case when subscriptionend is not null then 1 end) as canceled 
from [dbo].[LITAPROJECT 2 SQL]
```
---------



### Power BI Analysis 

Interactive dashboards and visuals for exploring subscription Metrics.

1.	Key Metrics Dashboards
-	KPI Cards : Displayed key metrics()
-	Interactive slicers: Added slicers for regions and subscription types, allowing viewers to filter insights by their area of interest.
2.	Subscriber Distribution and Segment Analysis
-	Subscription count by region and type : Visualized using interactive bar charts, showing which regions have the highest subscriptions revenue generated and subscription types that is most popular base on their revenue.
Customer segmentation dashboard: Created visuals to differentiate segments by region, subscription types, monthly trends, quarterly revenue.

### Data Analysis and Insight Generation

![Power Bi Visuals Screenshot 2024-11-19 113522](https://github.com/user-attachments/assets/903d3085-5175-448a-99bd-b27aa41051f1)

 The above Visualization shows some intriguing patterns and trends to understand customer’s behavior, track subscription types, and identifying key trends in cancellations and renewals of the various subscription types available in the company.
 
1. Subscription Trend:  Subscription numbers have shown significant fluctuations over time, with a sharp decline in September, where revenue plummeted from $6.75 million in August to just $3.37 million. Quarterly revenue reveals a concerning trend, decreasing from $20 million in the third quarter to only $10 million by the fourth. Annually, revenue has declined from $40 million in 2022 to $27 million in 2023, clearly illustrating a systematic downturn in purchases that demands attention.
   
RECOMMENDATION : Boost marketing efforts during peak periods to leverage customer interest. Introduce targeted promotions and membership discounts during slower periods to drive new sign-ups.

2. Subscription Type: The bar chart illustrates that the basic subscription tier dominates the market, representing 50% of total subscriptions and generating revenue of 34 million, encompassing both premium and standard plans. Analysis indicates that the basic subscription exhibits a cancellation rate of zero, underscoring its status as the preferred choice among consumers. This sustained popularity can likely be attributed to its cost-effectiveness and budget-oriented pricing structure.

RECOMMENDATION To enhance our outreach efforts, we should prioritize marketing the benefits of the basic subscription while simultaneously refining our other subscription offerings. Additionally, implementing strategic promotions, such as discounts and membership incentives, can be highly effective in encouraging customers to consider and purchase other subscription types.

3.	REGIONAL BREAKDOWN : The visuals highlighting the regional performance provided valuable insights. Firstly, while all regions generated the same revenue, their sales rates varied, with the East achieving the highest rate at 25.11% and the North the lowest at 24.90%. This variation suggests potential areas for improvement in sales strategies across the regions. Secondly, the East stands out as the only region without any recorded subscription cancellations. This indicates a successful approach to customer engagement and local marketing, which could serve as a model for other regions to enhance their subscriber retention efforts.
   ![Regional Breakdown](https://github.com/user-attachments/assets/9fa52dcc-de0a-4748-9d7b-e09182398f55)

   
RECOMMENDATION : Amplify marketing strategies in other regions by implementing successful tactics from the East region that have demonstrated strong results.

4. Average Duration: The average duration of subscriptions recorded each year is 365 days. This figure indicates a high level of satisfaction among subscribers with the services provided. The annual renewal of subscriptions suggests that customers find value in the offerings, demonstrating their commitment to the service over an extended period. This consistent renewal pattern reflects positively on the quality and reliability of the services rendered, ultimately contributing to subscriber retention and overall business success.

RECOMMENDATION : To maintain subscriber engagement over time, implement tactics such as surveys and periodic check-ins, given that the average duration per year is favorable

-------

### CONCLUSION

  The analysis presents valuable insights into customer behavior, preferences, and regional trends. The key findings indicate a diversity of customer needs across various regions, varying product preferences, and distinct demographic characteristics that influence purchasing behavior. In conclusion, the examination of customer data highlights the significance of a customer-centric approach. By tailoring strategies to address the specific needs of different customer segments, the company can position itself for sustained success, ensuring responsiveness to evolving customer expectations and maintaining competitiveness within the market.




