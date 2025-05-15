# -Taxi-Business-Performance-Report-Operational-Insights-Using-Power-BI
This repository documents the Taxi Business Performance Analysis conducted as part of a capstone project with MyDataClique Bootcamp. You can read the full article and detailed breakdown on Medium here:

🔍 Project Overview
This project leverages Power BI to evaluate and visualize key operational metrics for a taxi organization. The goal was to extract actionable insights from raw data, revealing patterns in revenue, trip activity, customer behavior, and retention across a 3-month period.

🧩 Problem Statement
The taxi company needed clarity on several performance areas:

How many trips were completed within the 3-month period?

What’s the total revenue generated, and what’s the average trip cost?

How long are trips taking on average, and how far are customers traveling?

What’s the customer retention rate across months?

These questions guided the dashboard design and analysis, helping the business better understand its performance and improve operational decision-making.

📁 Dataset
Source: MyDataClique Bootcamp Capstone Project

Period Covered: May–July 2024

Size: 1,000 rows, 22 columns

Type: Trip-level data containing customer IDs, driver IDs, timestamps, fares, tips, distance, and duration metrics

⚙️ Methodology
🧼 Data Cleaning
Conducted a quality check for missing values, duplicates, spelling errors, and outliers — none were found, confirming the dataset was in good shape.

Validated data types: Converted customer/driver/vendor IDs to text, timestamp fields to date/time, and numerical columns to whole number or decimal as needed.

🔧 Data Preparation
Split datetime columns: Extracted pickup date/time and drop-off date/time into separate fields using Power Query.

Built a custom Date Calendar using M code:

m
Copy
Edit
let
    StartDate = #date(2024, 5, 1),
    EndDate = #date(2024, 7, 31),
    FullDate = List.Dates(StartDate, Duration.Days(EndDate - StartDate) + 1, #duration(1, 0, 0, 0))
in
    FullDate
Transformed the list into a table and enriched it with columns like Month Name, Month Number, Week of Month, Day, and Day Name.

Created a date hierarchy for deeper time-based analysis.

📊 DAX Analysis
Crafted 10+ measures using DAX to bring the dataset to life. Key metrics included:

Total Revenue, Total Trips, Average Fare, Tip Amount, Trip Distance, Trip Duration, Active Customers, Average Revenue Per Trip

Retention Rate using a combination of DATEADD and FILTER logic

🖼️ Visualization
Designed an interactive Power BI dashboard tailored to answer the core business questions at a glance.

Focused on clarity and usability, allowing users to filter by time, observe trends, and spot high-performing or underperforming areas.

Visual elements included line charts, cards, clustered bars, and retention visuals to support strategic insights.

🔍 Key Insights
Consistent trip volume with slight monthly fluctuations

Stable revenue growth driven by returning customers

Average trip duration and distance remained steady — helpful for route optimization

Customer retention showed healthy month-over-month engagement, suggesting high satisfaction or convenience-driven loyalty

💡 Recommendations
Leverage data to incentivize repeat riders with loyalty programs.

Monitor trip durations to flag potential delays or inefficiencies.

Use average revenue and tip insights to coach drivers on service improvements.

Continue tracking monthly retention rate to spot churn patterns early.
