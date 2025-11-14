# **Telecom Churn Analysis**

## **Table of Contents**

1. [Introduction](#introduction)  
2. [Project Description](#Project-Description)
3. [Project Aim](#Project-Aim)
4. [About](#About)
5. [Tools Used](#Tools-Used)
6. [Data importation](#Data-importation)
7. [Data cleaning and transformation](#Data-cleaning-and-transformation)
8. [Data modelling](#Data-modelling)
9. [Data analysis](#Data-analysis)
10. [Data Visualization](#Data-Visualization)
11. [Key Insights](#Key-Insights)
12. [Recommendation](#Recommendation)
13. [Conclusion](#Conclusion)

## **Introduction**
This project analyzes customer churn data for a California-based telecommunications company serving over 7,000 customers. Customer churn represents a critical business challenge, directly impacting revenue, marketing ROI, and long-term growth. The analysis identifies patterns in customer behavior, service usage, and demographic factors to understand why customers leave and provide data-driven strategies for retention.

## **Project Description**
The project scope covers comprehensive customer data analysis across multiple dimensions including demographics, service types, billing methods, and geographic distribution. The approach involved data exploration, descriptive analytics, correlation analysis, and visualization to address specific business questions that align with stakeholder requirements. The analysis connects customer behavioral data with service characteristics to identify churn drivers.

## **Project Aim**
To identify the primary drivers of customer churn, segment at-risk customer profiles, quantify the financial impact of churn, and provide actionable recommendations to reduce customer attrition.

## **About the Dataset**
Source: STC database
Record Count: 7,043 rows and 38 columns customers for the telecommunication churn table and for zipcode 1671 rows and two columns
Key Fields/Columns:
-	Customer demographics (gender, marital status, location)
-	Service details (internet type, contract type, monthly charges)
-	Payment information (payment method, paperless billing)
-	Tenure and status (customer lifetime, churn status)
-	Total Revenue (total revenue, ARPU(Average annual Revenue Per User), churn revenue)
-	Geographic data (cities, performance by location)

## **Tools Used**
Power BI – For data cleaning, validation, modelling, normalization, interactive dashboard creation and visualization.

## **Importing the Dataset**
Data (“telecom customer churn and the telecom zip population” tables) were extracted from STC database in CSV format then imported into Power BI. Before loading the data was transformed in power query for cleaning, normalizing, then relationships were created between the customer details and zip code table and then loaded for interactive dashboard development. 

## **Data Cleaning & Transformation**
-	Categorical Inputation (Non-Churned Customers): Null entries within the Churn Category with “Customers” since they had the status of stayed and joined which means they are still existing customers and Churn Reason columns were replaced with the descriptive value "N/A". This decision reflects the business logic that an empty value in these specific fields signifies the customer is still active.
-	Numerical Imputation (Zero Replacement): Null values in quantitative fields, such as “Avg monthly GB download”, were systematically replaced using the zero-inputation method.
-	Created calculated fields: Generated churn flags, tenure segments, and revenue categories
-	Validated geographic data: Standardized city names and coordinated with zip code database

## **Data Modeling**
Power BI Relationships: After data transformation and normalization, the data was modelled by joining the fact table (telecom customer churn) was joined with the dimension table (telecom_zip_population) on the zip code with a one-to -many relationship

DAX Measures:
-	Churn rate: Calculate the percentage of customers who churned
-	Churn Revenue: Total amount of revenue lost due to churning
-	Total Customers: Counts the total number of customers.
-	Average revenue per user: Generates the average revenue for users

## **Data Analysis**
Key Metrics & KPIs Analyzed:
-	Overall churn rate (26.54%) and revenue churn rate (17.24%)
-	Customer demographics (gender, marital status distribution)
-	Service performance by type (Fiber Optic, DSL, Cable)
-	Contract type analysis (month-to-month vs. term contracts)
-	Payment method correlation with churn
-	Customer tenure segmentation and churn patterns
-	Geographic performance across 1,106 cities
-	Revenue impact by customer segment ($3.68M churn revenue)

## **Data Visualization**
Dashboard Page 1: Telecom Customer Analysis
-	KPI Cards: Total Customers (7,043), Churn Rate (26.54%), Total Revenue ($21.37M), Total number of cities (1106) and average monthly charge.
-	Stacked bar Chart: Churned Customers by Category (Competitor, Dissatisfaction, Attitude, Price, Other).
-	Donut Chart: Gender Distribution by churn customers
-	Stacked column Chart: Churn by Contract Type (Month-to-Month, One Year, Two Year)
-	Stacked Bar Chart: Top 10 cities by revenue
-	Donut Chart: Churn Rate by Marital Status 
-	Stacked Bar Chart: bottom 10 cities by revenue

Dashboard Page 2: Telecom Churn Service Analysis
-	KPI Cards: Total Customers (7,043), Total Revenue ($21.37M), Churned Revenue ($3.68M), Churn Rate (26.54%), annual average rate per user ($3034.38)
-	Stacked Bar Chart: Churned Customers by Internet Type (Fiber Optic: 1,236, DSL: 307, Cable: 213)
-	Donut Chart: Customers by Paperless Billing (Yes: 25.08%, No: 74.91%)
-	Stacked Column chart: Churned Customer by Online Security Status
-	Stacked Column chart: Churned Customer by Payment method.
-	Stacked Column chart: Churned Customer by Online backup.
-	Stacked Column chart: Churned Customer by Online Security Status.
-	Stacked bar chart: Customer tenure segment by status.


## **Key Insights**
- High Attrition Rate: The company has a churn rate of 26.54% (1,869 customers), significantly impacting its customer base.
- Primary Service Failure: Fiber Optic service is the biggest driver of churn, with 1,236 churned customers, pointing to critical service quality or expectation gaps.
- Contract Instability: Customers on Month-to-Month contracts are the most vulnerable, churning at a rate three times higher than those on annual contracts.
- Onboarding Crisis: New customers in the 0-3 month tenure segment exhibit the highest churn volume, indicating failures in the initial onboarding and service activation process.
- Geographic Financial Risk: Top revenue-generating cities like Los Angeles and San Diego are also the largest sources of churned customers, representing the highest absolute financial risk.
- Value Customer Loss: The 17.24% Revenue Churn Rate confirms that the company is losing high-value customers, not just low-revenue accounts.

## **Recommendations**
Immediate Actions (0-3 months):
•	Launch targeted retention campaign for Month-to-Month Fiber Optic customers in major metropolitan areas
•	Implement "First 90 Days" onboarding program with proactive support check-ins
•	Create contract conversion incentives to move high-risk customers to annual agreements
Strategic Initiatives (3-12 months):
•	Conduct comprehensive Fiber Optic service quality review and infrastructure assessment
•	Develop bundled service packages including Online Security to increase customer stickiness
•	Redesign billing communications for paperless billing customers to enhance engagement
Long-term Transformations (12+ months):
•	Build predictive churn modeling capability for proactive intervention
•	Establish cross-functional churn task force with representatives from product, support, and marketing
•	Implement customer success metrics tied to executive compensation

## **Conclusion**
The analysis reveals that churn is primarily driven by service quality issues in Fiber Optic internet, exacerbated by flexible contract terms that enable easy cancellation. The financial impact is substantial at $3.68M annually, with particular concentration in high-value urban markets. By implementing the recommended strategies focused on service improvement, contract stabilization, and targeted retention, the company can potentially reduce churn by 25% and recover approximately $900,000 in annual revenue while strengthening customer loyalty in core markets.


