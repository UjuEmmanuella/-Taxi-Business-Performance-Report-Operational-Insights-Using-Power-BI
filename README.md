# Taxi Business Performance Report And Operational Insights Using PowerBI
This repository documents the Taxi Business Performance Analysis conducted as part of a capstone project with MyDataClique Bootcamp. You can read the full article and detailed breakdown on Medium here:

👉 [Full Case Study on Medium: How I Built a Taxi Business Performance Report in Power BI](https://medium.com/@UjuEmmanuella/what-3-months-of-taxi-records-taught-me-about-business-intelligence-56e19c89fafa)

---

## 🔍 Project Overview

This project used Power BI to evaluate and visualize key operational metrics for a taxi organization. The goal was to extract actionable insights from raw data, revealing patterns in revenue, trip activity, customer behavior, and retention across a 3-month period.

---

## Problem Statement

The taxi company needed clarity on several performance areas:

* How many trips were completed within the 3-month period?
* What’s the total revenue generated, and what’s the average trip cost?
* How long are trips taking on average, and how far are customers traveling?
* What’s the customer retention rate across months?

These questions guided the dashboard design and analysis, helping the business better understand its performance and improve operational decision-making.

---

## 📁 Dataset

* **Source:** MyDataClique Bootcamp Capstone Project
* **Period Covered:** May–July 2024
* **Size:** 1,000 rows, 22 columns
* **Type:** Trip-level data containing customer IDs, driver IDs, timestamps, fares, tips, distance, and duration metrics

---

## Methodology

###  Data Cleaning

* Checked for missing values, duplicates, spelling errors, and outliers — none found.
* Validated and adjusted data types:

  * Converted customer/driver/vendor IDs to text
  * Converted timestamps to date/time
  * Adjusted numeric fields to whole numbers or decimals where necessary

###  Data Preparation

* **Datetime splitting:** Extracted pickup and drop-off date/time into separate fields using Power Query
* **Custom Date Calendar:** Created using M code:

```m
let
    StartDate = #date(2024, 5, 1),
    EndDate = #date(2024, 7, 31),
    FullDate = List.Dates(StartDate, Duration.Days(EndDate - StartDate) + 1, #duration(1, 0, 0, 0))
in
    FullDate
```

* Transformed the date list into a table and added columns like Month Name, Month Number, Week of Month, Day, and Day Name
* Built a date hierarchy for time-based analysis

### DAX Analysis

Created 10+ DAX measures to generate performance metrics:

* Total Revenue
* Total Trips
* Average Fare
* Tip Amount
* Trip Distance
* Trip Duration
* Active Customers
* Average Revenue Per Trip
* Retention Rate using a combination of `DATEADD` and `FILTER` logic

---

## Dashboard Visualization

Designed an interactive Power BI dashboard to answer the business questions at a glance.

* Focused on clarity, interactivity, and usability
* Enabled filtering by time and segmentation
* Used visuals such as line charts, cards, bar charts, and retention visuals
* Emphasized trends and highlighted high/low performing areas

---

## Key Insights

1. **Peak growth occurred from May to July, but there was no clear strategy for off-peak months.**
2. **Top vendors consistently outperformed others, signaling a need for standardizing best practices.**
3. **Revenue during non-surge hours was higher than during surge periods, showing surge pricing was counterproductive.**
4. **Commute trips were the lowest, indicating a missed opportunity to attract consistent, repeat customers.**
5. **Surge pricing was more common during fog and rain, not during snow when demand was actually highest.**

---

## 💡 Recommendations

* Develop off-season marketing campaigns or promotions to reduce revenue drop in off-peak months
* Analyze top vendors’ practices and replicate successful behaviors across all vendors
* Re-evaluate surge pricing to avoid customer drop-off during peak times
* Target commuters with loyalty programs or daily pass offers to boost repeat trips
* Align surge pricing strategy with actual demand trends observed in different weather conditions

---

##  Final Note

This project highlights the power of data storytelling and simple visuals to drive impactful decisions. This dashboard empowers the taxi business to optimize its strategy and improve both customer satisfaction and revenue stability by revealing hidden patterns in customer behavior, vendor performance, and pricing effectiveness.

---

📚 View detailed write-up on Medium → [Link](https://medium.com/@UjuEmmanuella/what-3-months-of-taxi-records-taught-me-about-business-intelligence-56e19c89fafa)

Interact with my Dashboard [here](https://app.powerbi.com/view?r=eyJrIjoiNzc5OTM1MjQtNDg4Ni00OGU0LTlmZWItMDhjMzM3NTRjOTU0IiwidCI6IjE0ODkzNGNiLWQyMDgtNGU1Ny1hNGNkLWE2YTY2YWIyMDgwMCJ9&embedImagePlaceholder=true&pageName=8fdf51b705422d29dea9)

---

### Business Performance Dashboard

![Business Performance Dashboard](./Business%20Performance%20Dashboard%20%26%20Operational%20Insights/Business%20Performance%20Dashboard.png)

### Operational Insights

![Operational Insights](./Business%20Performance%20Dashboard%20%26%20Operational%20Insights/Operational%20Insights.png)

