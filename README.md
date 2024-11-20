# Customer's Subscription Plans
## Content
- [Introduction](#introduction)
- [Data Description](#data-description)
- [Basic Statistics in the Dataset](#basic-statistics-in-the-dataset)
- [Methodology](#methodology)
- [Using Microsoft Excel for Analysis](#using-microsoft-excel-for-analysis)
- [Analysing with Sql](analysing-with-sql)
### Introduction: 
 In today’s dynamic marketplace,it is crucial to have an understanding of customer subscription behaviour to enable Subscription-based businesses to foster long-term growth and strengthening customer commitment.Analyzing data like this creates a significant opportunity for businesses by utilizing data insights to refine marketing strategies and enhance customer experiences. This project investigates customer subscription plans to uncover patterns that impact cancellations and retention. The dataset consists of transaction records and associated information. By utilizing tools like: Excel , SQL( Structured Query Language) and Power BI. The dataset was carefully cleaned, analyzed, and visualized, providing a clearer perspective of the company's subscription dynamics and revealing opportunities for enhancement.

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

### Basic Statistics in the Dataset
1. Total Revenue: #6.75Million
2. Total Number of Customers: 33,787
3. Average Revenue: #1,999
4. Subription duration: 365days
5. Number of Regions: 4

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


