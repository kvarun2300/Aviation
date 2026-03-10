### U.S. Airline Performance & Delay Analysis Report

## 1. Introduction

Flight delays and cancellations are major challenges in the aviation industry. They impact passenger satisfaction, airline efficiency, airport operations, and the broader economy. The objective of this project is to analyze historical U.S. airline flight data to identify patterns in delays and cancellations, evaluate airline and airport performance, and generate actionable insights using data analytics tools.

This project uses SQL for data cleaning and analysis, and Power BI for visualization and dashboard development.

---

## 2. Objectives

The primary objectives of this analysis are:

* Analyze historical flight data to understand delay and cancellation patterns.
* Identify major causes of flight delays.
* Evaluate airline performance using key performance indicators.
* Analyze flight trends across time such as month, day, and time of day.
* Develop an interactive dashboard to present insights clearly.

---

## 3. Dataset Overview

The dataset contains detailed information about flights operating in the United States.

Key dataset statistics:

* Total Flights: 5 Million
* Total Airports: 322
* Total Airlines: 14
* Cancelled Flights: 87,000
* Delayed Flights: 1 Million

Important columns in the dataset include:

* Flight date
* Airline code
* Origin airport
* Destination airport
* Scheduled departure time
* Arrival delay
* Departure delay
* Cancellation status
* Cancellation reason
* Delay categories such as airline delay, weather delay, and NAS delay.

---

## 4. Data Cleaning and Preparation (SQL)

### 4.1 Time and Date Handling

In the raw dataset, scheduled departure time was stored in HHMM format. To enable time-based analysis, the time was converted into a proper datetime format by combining the year, month, day, and scheduled departure time.

A new column called FLIGHT_DATE was created to simplify time-based analysis such as monthly and daily trends.

### 4.2 Handling Missing Values

Several columns contained missing values. Different strategies were used depending on the column:

* Delay columns were replaced with 0 where delays were not recorded.
* Cancellation reason values were kept as NULL when flights were not cancelled.

This ensured accurate aggregation and statistical calculations.

### 4.3 Data Enrichment

To improve readability, the cancellation reason codes were converted into descriptive values.

Cancellation Reason Mapping:

A – Airline
B – Weather
C – National Air System
D – Security

This allowed easier interpretation during analysis and visualization.

### 4.4 Data Integration

Multiple tables were joined to create a unified analytical dataset. The following tables were integrated:

* Flights
* Airlines
* Airports

Airport tables were joined twice to capture both origin and destination details. The final integrated dataset was stored as a SQL view to simplify analysis.

---

## 5. Exploratory Data Analysis (EDA)

Using SQL queries, several exploratory analyses were conducted.

### 5.1 Flight Volume Analysis

The dataset contains approximately 5 million flights. Among these:

* Around 1 million flights experienced delays.
* Approximately 87,000 flights were cancelled.

This indicates that delays are a common operational issue in the aviation industry.

### 5.2 Delay Statistics

Statistical analysis of arrival delays was performed to understand delay distribution.

Metrics calculated include:

* Average arrival delay
* Maximum delay
* Minimum delay
* Median delay

The average arrival delay across all flights was approximately 4.89 minutes.

### 5.3 Delay Cause Analysis

Different delay categories were analyzed to determine the main contributors to delays.

Major delay categories include:

* Airline delays
* Weather delays
* National Air System (NAS) delays
* Security delays

The analysis shows that airline operational issues and weather conditions are among the major causes of delays.

---

## 6. Key Performance Indicators (KPIs)

Several KPIs were defined to evaluate airline performance.

### On-Time Performance (OTP)

On-time performance measures the percentage of flights arriving within 15 minutes of their scheduled arrival time.

OTP Rate = On-Time Flights / Total Flights

Current OTP Rate: 63%

### Average Arrival Delay

This KPI measures the average delay in minutes for arriving flights.

Average Arrival Delay: 4.89 minutes

### Cancellation Rate

Cancellation Rate = Cancelled Flights / Total Flights

Current Cancellation Rate: 2%

### Delay Contribution

This metric measures the percentage contribution of each delay type to the total delay.

---

## 7. Dashboard Development

The cleaned dataset was connected to Power BI for visualization.

### Data Modeling

Relationships were created between:

* Flights
* Airlines
* Airports

DAX measures were created to calculate key KPIs including:

* Total Flights
* Average Delay
* On-Time Rate
* Cancellation Rate

---

## 8. Dashboard Overview

The dashboard presents a comprehensive overview of airline performance and delay patterns.

Key components include:

### KPI Summary

The top section displays major KPIs including total flights, total airlines, cancelled flights, delayed flights, on-time percentage, cancellation rate, and average arrival delay.

### Airline Performance

A bar chart compares airlines based on their average arrival delay to identify which airlines perform better.

### Delay Reasons

A visualization shows the distribution of delays by category, helping identify the major causes of delays.

### Time-Based Analysis

Flight performance is analyzed across different time periods including:

* Day of the week
* Month of the year
* Time of day

### Flight Volume Analysis

Charts display the number of flights operated by each airline and by time range.

### Interactive Filters

The dashboard allows users to filter data by:

* Airline
* Airport
* Month
* Day
* Cancellation reason

These filters allow deeper exploration of the data.

---

## 9. Key Insights

Several insights were derived from the analysis:

* Approximately 63% of flights arrive on time.
* Evening flights experience higher delays compared to morning flights.
* Some airlines consistently perform better than others in terms of delay management.
* Weather and airline operational issues are major contributors to delays.
* Weekend flight volumes tend to be lower compared to weekdays.

---

## 10. Conclusion

This project demonstrates how data analytics can be used to analyze large-scale aviation data and generate meaningful insights.

By combining SQL for data processing and Power BI for visualization, the project provides a comprehensive view of airline performance and delay patterns.

The interactive dashboard enables stakeholders to monitor operational efficiency, identify delay causes, and make informed decisions to improve airline performance and passenger experience.

---

## 11. Tools and Technologies Used

* SQL (Data Cleaning, Data Integration, EDA)
* Power BI (Dashboard Development and Visualization)
