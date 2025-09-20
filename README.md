Of course! Here is a professionally formatted README for your "Credit Card Financial Weekly Dashboard" project, styled like the example you provided.

💳 Credit Card Financial Weekly Dashboard
This project is a Business Intelligence dashboard designed to provide a comprehensive weekly overview of credit card performance. It transforms raw customer and transaction data from a SQL database into actionable insights using Power BI.

The goal is to empower stakeholders with real-time analytics to monitor key metrics, identify trends, and support strategic decision-making.

🚀 Key Features
Interactive Dashboard: A dynamic Power BI interface for deep-dive analysis.


Performance Tracking: Monitors crucial metrics like revenue, transaction volume, activation rates, and delinquency rates.



Customer Segmentation: Segments customers by age, income, and gender for targeted insights.




Week-over-Week Analysis: Compares current week performance against the previous week to track growth and trends.


🛠️ Tech Stack & Tools

Database: SQL 


Business Intelligence & Visualization: Power BI 


Data Analysis & Modeling: DAX (Data Analysis Expressions) 


📊 Key Insights & Findings

Overall Revenue (YTD): The total year-to-date revenue is $57M.


Revenue Components (YTD): Driven by $46M in transaction volume and $8M in interest earned.


WoW Growth: Revenue saw a significant 28.8% increase in Week 53.


Demographic Performance: Male customers contribute more to revenue ($31M) compared to females ($26M).


Product Usage: Blue & Silver cards are the most popular, accounting for 93% of all transactions.


Geographic Concentration: TX, NY, & CA are top-performing states, contributing 68% of the business.

Core Health Metrics:

Overall Activation Rate: 

57.5% 

Overall Delinquent Rate: 

6.06% 

⚙️ DAX Implementation
Custom DAX queries were written to create calculated columns and measures for advanced analysis:

Customer Segmentation:

Code snippet

// Age Group Segmentation
AgeGroup = SWITCH(
    TRUE(),
    'public cust_detail'[customer_age] < 30, "20-30",
    'public cust_detail'[customer_age] < 40, "30-40",
    'public cust_detail'[customer_age] < 50, "40-50",
    'public cust_detail'[customer_age] < 60, "50-60",
    "60+"
)
Code snippet

// Income Group Segmentation
IncomeGroup = SWITCH(
    TRUE(),
    'public cust_detail'[income] < 35000, "Low",
    'public cust_detail'[income] < 70000, "Med",
    "High"
)
Week-over-Week Revenue Calculation:

Code snippet

// Current Week Revenue
Current_week_Reveneue = CALCULATE(
    SUM('public cc_detail'[Revenue]),
    FILTER(
        ALL('public cc_detail'),
        'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])
    )
)

// Previous Week Revenue
Previous_week_Reveneue = CALCULATE(
    SUM('public cc_detail'[Revenue]),
    FILTER(
        ALL('public cc_detail'),
        'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2]) - 1
    )
)
🎯 Project Outcome
The project culminated in a powerful, interactive dashboard that successfully streamlines data processing to monitor key financial metrics. It delivers clear, actionable insights to stakeholders, enhancing their ability to make informed, data-driven decisions for the credit card division.


👨‍💻 Author
Shobhit Raj Dahiya

💼 LinkedIn

📂 GitHub
