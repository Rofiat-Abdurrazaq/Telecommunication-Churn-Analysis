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
Source: SkillsToCareer database

Record Count: 
- Telecom Customer Churn Table: 7,043 rows, 38 columns.
- Zip Code Population Table: 1,671 rows, 2 columns.

Key Fields/Columns:
-	Customer demographics (gender, marital status, location)
-	Service details (internet type, contract type, monthly charges)
-	Payment information (payment method, paperless billing)
-	Tenure and status (customer lifetime, churn status)
-	Total Revenue (total revenue, ARPU(Average annual Revenue Per User), churn revenue)
-	Geographic data (cities, performance by location)

## **Tools Used**
- Power BI: Used for end-to-end data processing, including cleaning, transformation, data modeling, and the creation of interactive dashboards and visualizations.
  
## **Importing the Dataset**
The "telecom customer churn" and "telecom zipcode population" tables were extracted as *.CSV* files from the STC database and imported into Power BI's Power Query Editor. The data was transformed and cleaned before being loaded into the data model, where relationships were established to enable interactive dashboard development.

## **Data Cleaning & Transformation**
-	Categorical Inputation (Non-Churned Customers): Null entries within the Churn Category were replaced with “Customers” since their status was *stayed and joined* which means they are still existing customers, and Churn Reason columns were replaced with the descriptive value *"N/A"*. This decision reflects the business logic that an empty value in these specific fields signifies the customer is still active. Some null values were found in other services columns that were replaced with *"unverified"* because they were a boolean response of *"yes or no"*.
-	Numerical Imputation (Zero Replacement): Null values in quantitative fields, such as *Avg Monthly GB Download*, were replaced with 0.
-	Created calculated fields: Generated churn flags, tenure segments, and revenue categories.
-	Geographic Validation: Standardized city names and ensured proper coordination with the zip code database.

## **Data Modeling**
Power BI Relationships: Established a *one-to-many* relationship between the telecom_zipcode_population dimension table and the telecom_customer_churn fact table using the Zip Code field.

DAX Measures:
-	Churn rate:  Calculates the percentage of customers who churned.
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
-	KPI Cards: Total Customers (7,043), Churn Rate (26.54%), Total Revenue ($21.37M), Number of Cities (1,106), Avg Monthly Charge ($63.60).
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

## **Recommendations by Stakeholders**
- CEO & Executive Team: Prioritize resolving the Fiber Optic service issues, combining a competitive market analysis and interviews, to understand why customers are leaving in cities like San Diego and Los Angeles.
- Head of Marketing:  Immediately launch two campaigns; a short-term promotion for Month-to-Month Fiber customers to reduce churn without eliminating the product, and a long-term project to conduct interviews with churned customers to pinpoint if they left for competitors, price, or service quality.
-  Head of Customer Service: Create a fast-track support specifically for Fiber Optic customers, especially in the San Diego branch
- Product & Service Development Team: Conduct a root-cause analysis of Fiber Optic support tickets to identify the top 3 technical or experience failures (e.g., installation delays, speed inconsistencies).
- Finance Team: Provide funding for the proposed retention campaigns and market research by modeling their cost against the $3.68M in lost revenue, and work with product teams to analyze the profitability of the Month-to-Month segment to determine if it's worth saving. 


## **Conclusion**
The analysis confirms that customer churn is primarily driven by performance issues in the Fiber Optic internet service, intensified by flexible Month-to-Month contracts that allow dissatisfied customers to leave with ease. Fiber Optic alone accounts for 1,236 churned customers, exceeding all other services, especially in competitive markets like San Diego and Los Angeles. A significant portion of these customers are not just leaving the service; they are switching to competitors. This signals a deeper market problem: our Fiber Optic offering is not meeting customer expectations compared to alternatives. The financial impact is substantial, with an estimated $3.68M in annual revenue lost.

To reverse this trend, the company must focus on improving service performance, strengthening contract structures, and implementing proactive retention strategies. Targeted promotional offers can also help stabilize customers currently on Month-to-Month plans. Most importantly, a thorough market and competitor analysis is essential. Understanding why customers prefer competing providers and where our product experience falls short will guide the redesign of the Fiber Optic service and ensure we address the true root causes of churn. With these actions, the company can reduce churn while rebuilding customer trust and loyalty.




