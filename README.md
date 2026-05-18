# END-TO-END-SALES-PERFORMANCE-AND-PROFITABILITY-ANALYSIS

## BACKGROUND AND SCENARIO
This project analyses 20,000 transactions across 600 customers from January to December 2023 of a beverage distribution company operating across 10 stores in the United States, selling 8 product categories including Coffee, Tea, Soft Drinks, Water, Sports Drinks, Energy Drinks, Alcoholic Beverages, and Juice.

<img width="1230" height="687" alt="image" src="https://github.com/user-attachments/assets/08a14fff-715e-4b59-8365-8318bbd9b1b5" />



## TABLE OF CONTENTS

1. [Background and Scenario](#background-and-scenario)
2. [Project Overview](#project-overview)
3. [Business Problem](#business-problem)
4. [Dataset Overview](#dataset-overview)
5. [Data Cleaning Process](#data-cleaning-process)
6. [Data Modelling](#data-modelling)
7. [DAX Measures Calculated and Their Business Importance](#dax-measures-calculated-and-their-business-importance)
8. [Insights and Recommendations](#insights-and-recommendations)
9. [Limitations](#limitations)
10. [How This Project Improved My Skills](#how-this-project-improved-my-skills)
11. [Challenges Faced During the Project](#challenges-faced-during-the-project)
12. [Conclusion](#conclusion)
13. [Author](#author)

## PROJECT OVERVIEW
This project is a complete end-to-end sales analytics solution built entirely in Microsoft Excel using:

  -	Power Query Editor (Data Cleaning & Transformation)
  
  -	Power Pivot (Data Modeling & DAX)
  
  -	Pivot Tables & Pivot Charts
  
  -	Interactive Dashboard Design

The goal of the project was to transform raw transactional sales data into an executive-level business intelligence solution capable of answering:
  -	Is the business profitable?
  
  -	Which categories drive revenue and profit?
  
  -	Where is the business losing money?
  
  -	Which locations and salespeople perform best?
  
  -	What customer segments generate the most revenue?
  
  -	How do operational drivers explain financial performance?

The project was divided into two dashboards to properly represent the datset:

  1.	Executive Profitability Dashboard
     
  2.	Customer & Operational Analysis Dashboard
     
## BUSINESS PROBLEM

Modern businesses generate massive transactional data daily, but raw data alone does not support decision-making.

Management need to understand:

  -	Whether revenue growth is sustainable or being eroded by rising costs
  
  -	Which product categories are genuinely profitable versus which consume resources for minimal return
  
  -	How salesperson and store performance compares — both by revenue and by margin efficiency
  
  -	Which customer segments drive the most revenue and what concentration risks exist
  
  -	Where geographic and demographic opportunities are being underutilised
  
### PROJECT OBJECTIVES
  
  - Connect disparate data sources- Loaded 4 CSV files into Power Query, cleaned each independently, loaded all to the Data Model
    
  - Model relationships between tables - Built a Star Schema in Power Pivot connecting Fact Table to 3 dimension tables via foreign keys
    
  - Write sophisticated DAX measures-  measuresBuilt 20+ DAX measures including net calculations, time intelligence, and ratio metrics
    
  - Summarise findings in dynamic pivot tables - Built 15+ pivot tables covering performance, profitability, customer segments, and geography
    
  - Create an interactive dashboard - Built 2 fully interactive Excel dashboards with timeline slicer controlling all visuals simultaneously

### TOOLS AND SKILLS USED 

  -	Microsoft Excel-Power Pivot - Star schema data modelling, relationship management
    
  -	Power Query Editor - Data connection, cleaning, transformation, Calendar Table creation
    
  -	Pivot Tables- Data summarisation and analysis
    
  -	Pivot Charts- Visual storytelling and interactive dashboard design
    
  -	DAX (Data Analysis Expressions)- KPI measures, time intelligence, ratio calculations

## DATASET OVERVIEW

  - **Fact Table** - with 20,000 rows and Columns such as Order Date, Product ID, Customer ID, Sales Person ID, Quantity Sold, Quantity Returned, Payment Method.

  - **Products Table** - with 100 rows and columns such as Product ID, Product Name, Category, Sales Price, Cost Price

  - **Salesperson Table** - 10 rows and columns included Sales Person ID, First Name, Last Name, Store Name, Date of Birth

  - **Customers Table** - 600 rows and columns such as Customer ID, First Name, Last Name, Gender, Location, Date of Birth.

### Key dataset characteristics:

  - Date range: January 1 – December 30, 2023
  
  - 20 US states covered
  
  - 8 product categories, 100 individual products
  
  - 10 stores, 10 salespersons
  
  - Payment methods: Cash, Credit Card, Debit Card, Online Payment

<img width="1146" height="575" alt="fact table only  pq" src="https://github.com/user-attachments/assets/9bb9f5af-1f7c-4dea-859b-7748b996dc31" />


## DATA CLEANING PROCESS
### DATA CLEANING AND TRANSFORMATION USING POWER QUERY

1. **Removed Duplicate Records**

Duplicate date entries initially caused relationship issues during data modeling. A proper Date Dimension table was created by extracting unique dates from the transactional dataset contained in the facts table.

<img width="1593" height="632" alt="date PQ" src="https://github.com/user-attachments/assets/2d0c0e74-42ba-4766-8b53-c607d81836ba" />

2. **Created Time Intelligence Columns**

Generated:
  - Month Name
  - Month Number
  - Quarter
  - Week
  - Year

The Month Name column was sorted using Month Number to ensure chronological ordering in Pivot Tables and charts.

<img width="1593" height="632" alt="salesperson PQ" src="https://github.com/user-attachments/assets/9d5eef7f-b0e1-453d-8a09-5ec69706310f" />


3. **Created Customer Segments** - Age groups and Age Bracket were also created for demographic analysis

Customers were segmented into:

  - Gen Z
  - Millennials
  - Gen X
  - Boomers

<img width="1596" height="637" alt="cust PQ" src="https://github.com/user-attachments/assets/52bbfa39-3bf6-46ca-a77f-d55b242c1fa3" />


4. **Standardized column for Net calculations called Net Quantity and also created consistent calculations for**:

  - Revenue
  - COGS
  - Gross Profit
  - Profit Margin
  - Return-adjusted metrics

<img width="1592" height="612" alt="fact pq" src="https://github.com/user-attachments/assets/bc346f61-825e-4658-975f-5bfde469fd09" />

### DATA MODELLING 

This project used a Star Schema, a central Fact Table surrounded by Dimension Tables, connected via foreign keys.The raw data came as four separate tables with no pre-built relationships and a fifth table was created to represent the date table for time intelligence

Modelling relationships allows DAX measures to query across all tables simultaneously — answering questions like "which customer generation buys the most Tea?" without manually merging any data.

<img width="1162" height="653" alt="diagram" src="https://github.com/user-attachments/assets/b83c8e9c-e244-479d-97b8-f0e895fefaa0" />


### DAX MEASURES CALCULATED AND THEIR BUSINESS IMPORTANCE

1. **Revenue & Top-Line Performance**

  - TOTAL REVENUE (The foundational gross sales metric)
  
  - NET REVENUE (Actual revenue earned after returns)
  
  - REVENUE LOSS TO RETURN (Direct leakages from top-line revenue)

2. **Profitability & Costs**
   
  - TOTAL COGS (Cost of Goods Sold, the primary expense)
  
  - GROSS PROFIT (Revenue minus COGS; baseline profitability)
  
  - PROFIT MARGIN (The efficiency of turning revenue into profit)

3. **Sales Volume & Returns**
   
  - NET QTY SOLD (Physical volume driving the revenue)
  
  - RETURN RATE (Product performance and quality health check)

4. **Month-over-Month (MoM) Growth Metrics**
   
These compare the current month's performance to the Prior Month (PM) to show business momentum:

  - MOM NET REVENUE
  
  - MOM GROSS PROFIT
  
  - MOM COGS
  
  - MOM NET QTY SOLD

5. **Previous Month (PM) Baseline Measures**
   
These are the technical calculations supporting the MoM growth metrics above:
  
  - PM NET REVENUE
  
  - PM GROSS PROFIT
  
  - PM COGS
  
  - PM NET QTY SOLD

6. **Customer & Salesperson Insights**
   
  - TOTAL CUSTOMERS (Size of the active customer base)
  
  - AOV (Average Order Value - how much a customer spends per transaction)
  
  - REVENUE PER CUSTOMER (Customer lifetime value/worth)
  
  - TOP SALESPERSON BY REVENUE (Individual performance tracking)

<img width="605" height="557" alt="new measures" src="https://github.com/user-attachments/assets/9be4d667-a34a-4633-905b-4299d85e9fa2" />


## INSIGHTS AND RECOMMENDATIONS

### INSIGHTS 

   **Revenue & Profitability**

  - Net revenue reached $5.01M for 2023, with gross profit of $2.11M at a 42.1% margin — a healthy result, but margin is under quiet pressure as COGS grew at         9.1% MoM versus revenue at 8.8% which shows costs are rising faster than income.
  
  - $438K in revenue was lost to returns representing the gap between gross sales of $5.45M and net revenue. At an 8% return rate, this is recoverable and            worth investigating by product category.
    
    **Product Performance**

  - Tea is the most profitable category at 75.1% margin, yet ranks only 5th in revenue at $449K. A 20% uplift in Tea sales would add approximately $67K in profit     at near-zero additional cost, this is the highest-return action available in the data.
  
  - Juice is a drain on resources, generating only 13.4% margin on $353K revenue, yielding just $42K profit annually. It consumes shelf space, inventory, and        salesperson effort for less than 2% of total profit.
  
  - Soft Drink leads revenue at $1.1M with a strong 58% margin. it is the business's most valuable volume category.
  
  **Store & Salesperson Performance**

  - Crystal Franco at Myers-Lopez leads revenue at $519K, but Dustin Manning at Novak PLC leads profit margin at 43.4% despite ranking 9th in revenue — he sells      a smarter product mix. Understanding his category breakdown could unlock margin gains across other stores.

  - All 10 stores fall within a 7.5% revenue band ($483K–$519K) which is unusually flat for a 10-store operation, suggesting a shared operational ceiling worth       investigating.

 **Customer and Geographic Insights**

  - Gen X and Millennials together drive 60% of revenue ($3.01M combined). Baby Boomers contribute $1.25M but represent a declining demographic, Gen Z at only        $748K signals an underdeveloped pipeline that needs investment now.

  - Washington leads all states in profit margin at 44.6% despite ranking 4th in revenue. Its customers buy a more profitable product mix. Replicating                Washington's product emphasis in Michigan, the revenue leader could add $90K+ in annual profit with no new customer acquisition.

  - Male customers generate $2,568,282 (51.3%) and Female customers $2,440,230 (48.7%) — a near-equal split indicating healthy gender diversification with no   
    over-reliance on either segment.

  **Payment Method Insight**
  - Payment methods are evenly distributed across Online (25.5%), Credit Card (25.2%), Cash (24.8%), and Debit Card (24.5%). 
    This is a healthy diversification with no single channel risk.

  ## RECOMMENDATIONS

  - Push Tea aggressively, a 75.2% margin with only 5th-place revenue is the clearest missed opportunity. Promote Tea through salesperson incentives, bundle          deals,and featured placement. A 20% uplift in Tea revenue from $449K to $539K would add approximately $68K in profit at near-zero additional cost.
  
  - Review Juice and Alcoholic Beverage SKUs: combined, these two categories generate $127,125 in profit from $752,814 in revenue (16.9% blended margin). 
    Audit individual SKUs, reprice the lowest-margin products, or replace them with higher-margin alternatives. Resources deployed here would generate far            greater returns in Tea, Soft Drink, or Sports Drink.
  
  - Investigate the COGS growth rate — at 9.1% MoM versus revenue at 8.8%, costs are compounding faster than income. Identify which categories are driving the        COGS increase and whether supplier pricing or product mix shift is the root cause.
  
  - Study Dustin Manning's product mix, at 43.3% margin from 9th-place revenue, he sells smarter than almost everyone. His Tea revenue of $53,253 at 75.9% margin     is the category highlight. Understanding and coaching his approach across the team could recover $10K+ in profit without any volume increase.
  
  - Build a Gen Z acquisition strategy now, at 14.9% of revenue and declining as a share, this segment needs investment before the gap widens. Energy Drink           (37.2% margin) and Sports Drink (48.7% margin) both index well with younger demographics and carry strong margins which is a natural entry point for Gen Z-       targeted promotions.

  - Replicate Washington's product mix in high revenue states. Washington customers gravitate toward higher margin products. Run the same category emphasis as a      targeted promotion in Michigan and Virginia the top two revenue states to convert volume leadership into margin leadership.
  
  - Investigate the return rate by category, the overall 8.0% rate costs $438,298 annually. If one or two categories are driving disproportionate returns (Tea's      8.3% vs Coffee's 7.8% suggests variation exists), targeted quality or customer-targeting improvements in the worst-performing category could recover $50K+ in     revenue.
  
  - Investigate the shared $36,517 ceiling across all 10 stores — the unusually flat performance band suggests a common constraint affecting all stores equally.      Whether it is a shared inventory system, supplier limitation, or customer base overlap, identifying and removing this ceiling is the highest-potential            operational action available.

### DASHBOARDS DESIGNS / VISUALIZATIONS

### WIREFREAMING

Before building anything in Excel, I planned the dashboard layout in excel, mapping out which chart goes where and why. This step ensured the final dashboard tells a logical story rather than being a random collection of visuals.

<img width="1227" height="683" alt="image" src="https://github.com/user-attachments/assets/6e578083-f558-4fbd-b962-a18c4e74f5df" />


<img width="1245" height="657" alt="image" src="https://github.com/user-attachments/assets/4a9a5fd8-3554-413c-8db1-03af3e6c50be" />

### DASHBOARD DESIGNS

1. **Sales Performance and Profitability analysis**
   
  - Financial Health Check: Comprehensive view of net revenue, cost of goods sold (COGS), and overall gross profit margins.
  
  - Month-over-Month (MoM) Dynamics: Dynamic trend metrics tracking monthly growth and performance against previous month baselines.
  
  - Geographic Profit Mapping: Spatial visualization mapping regional revenue volume against state-level profit efficiency.
  
  - Product Category Performance: Deep-dive analysis separating high-volume scale categories from high-margin cash cows.
   

<img width="1230" height="687" alt="image" src="https://github.com/user-attachments/assets/57f8e873-d1be-47d8-a646-b66d3ae48646" />


2. **People, Customer and Segment Analysis**

  - Salesperson Efficiency Leaderboard: Performance evaluation comparing raw revenue volume against true gross profit contribution.
  
  - Demographic Segmentation: Breakdown of purchasing power and revenue concentration across generational brackets and gender.
  
  - Transactional Channel Analysis: Evaluation of customer payment methods to monitor revenue distribution and pipeline risk.
  
  - Customer Lifetime Value Metrics: High-level tracking of active customer counts, revenue per customer, and average order value.

<img width="1279" height="655" alt="image" src="https://github.com/user-attachments/assets/8006cd2b-b92e-4601-bf7e-7ea50e3de2ba" />


  ### LIMITATIONS

  - The dataset covers January–December 2023 only. Year-over-year comparison and multi-year trend analysis are not possible.
    
  - No operating cost breakdown. The COGS is available but there is no breakdown of fixed costs, overheads, rent, or staff costs. True net profit margin cannot       be calculated.
    
  - No individual customer transaction history which means purchase frequency per customer is not tracked. Repeat purchase rate, customer loyalty, and lifetime       value analysis are not possible.
    
  - No competitor or market data — Performance cannot be benchmarked against industry standards or competitors in the same geographic markets.
    
  - Static store assignment: Each salesperson is assigned to one store. The data cannot distinguish whether performance differences are driven by the individual      or by their store's geographic market.

### HOW THIS PROJECT IMPROVED MY SKILLS

  - Data modeling: Grouping and connecting different data tables together behind the scenes so your sales, customers, and products can connect to each other          seamlessly.
  
  - Power Query transformations: Doing the heavy lifting of cleaning up messy data, removing errors, and shaping it so it is perfectly organized for analysis.
  
  - DAX calculations: Writing custom formulas to compute complex business metrics that standard Excel tools cannot handle on their own.
  
  - KPI engineering: Building scorecard tiles that instantly tell a business owner if their main goals are on track, behind, or improving compared to last month.
  
  - Executive reporting: Packing dense data into high-level, clear summaries so busy managers and directors can make fast, accurate decisions.
  
  - Customer segmentation: Breaking down the buyer base into distinct groups, like generations or gender, to figure out exactly who is driving the most profit.
  
  - Profitability analysis: Digging beneath surface-level sales totals to find out which items, locations, or team members are actually making the most net           profit.
  
  - Time intelligence calculations: Setting up dynamic formulas to compare this month's sales to the previous month or track growth over time

### CHALLENGES FACED DURING THE PROJECT

Some notable technicl challenges faced and solved during the project included:
- Handling custom number formatting
- Structuring executive dashboards for data storytelling
- Binding pivot data to bing maps visualizations

These challenges significantly improved understanding of real-world analytics workflows.

### CONCLUSION

This project converted multi-source transactional datasets into a centralized business intelligence solution. By building this analytical model, I was able to:

  - Pinpoint high-value revenue streams: Isolated Soft Drinks as the primary scale engine at $1.1M in sales, while exposing Tea as an underutilized asset with an     exceptional 75.2% profit margin.
  
  - Map out operational and regional efficiency: Identified that Washington achieves the highest profitability rate (44.6%) by shifting consumers toward a better     product mix, outpacing higher-volume regions.
  
  - Segment target demographics: Evaluated purchasing behaviors to find that Gen X and Millennials anchor the business by generating 60.2% of total net income.
  
  - Quantify financial leakage: Discovered a major 8.0% return rate costing the company $438,298 annually, creating a clear, zero-cost target for revenue             recovery.

The final Excel dashboard built from scratch using Power Query, Star Schema data modeling, and 20+ DAX measures allows the company make informed and strategic decisoins that drives the company's growth.


### AUTHOR
Halimat Hammed

_Business, Sales and Financial Analyst_






























































