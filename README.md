# Service Booking Cancellation & Delay Analysis

## Business Question

Which times, areas, and service types have the most cancellations, and what operational changes could reduce them?

## Dataset

The project uses the **Ola Ride Bookings Dataset** from Kaggle.

The ride-hailing dataset is used as a stand-in for a service marketplace. Ride bookings represent service requests, while vehicle types are treated as service categories.

## Tools

- SQL / SQLite
- Microsoft Excel
- GitHub

## Analysis Approach

1. Imported the CSV dataset into SQLite.
2. Checked for duplicates and missing values.
3. Removed the CSV header artifact from the imported data.
4. Created a cleaned analysis table.
5. Created helper fields for booking hour, day of week, and cancellation flag.
6. Analyzed cancellation rates by hour, day, pickup area, and service type.
7. Used `RANK()` to identify the highest-risk area/service segments.
8. Used `LAG()` to analyze week-over-week cancellation changes.
9. Built an Excel dashboard to communicate the results.

## Key Findings

### 1. Peak cancellation hour

10 AM had the highest cancellation rate at **29.95%**, compared with the overall cancellation rate of **28.08%**.

### 2. Highest-risk pickup area

Vijayanagar had the highest cancellation rate among areas with at least 100 bookings, at **30.43%**.

### 3. Highest-risk service type

eBike had the highest cancellation rate among vehicle/service types, at **28.39%**.

## Overall KPIs

- Total bookings: **103,024**
- Completed bookings: **63,967**
- Cancelled bookings: **28,933**
- Overall cancellation rate: **28.08%**
- Average V_TAT: **170.88**
- Average C_TAT: **84.87**

## Recommendations

### 1. Focus on peak-hour operations

Review provider availability and dispatch performance around **10 AM**, when the cancellation rate reaches 29.95%.

### 2. Investigate high-risk areas

Investigate provider availability, demand patterns, and cancellation reasons in **Vijayanagar**, which has the highest area-level cancellation rate.

## Dashboard

The Excel dashboard contains:

- Total bookings KPI
- Cancellation rate KPI
- Cancelled bookings KPI
- V_TAT KPI
- Cancellation rate by hour
- Cancellation rate by pickup area
- Cancellation rate by service type
- Weekly cancellation trend

## Important Data Limitation

The source dataset contains V_TAT and C_TAT fields, but they do not provide a reliable actual-versus-promised arrival timestamp. Therefore, this project reports V_TAT and C_TAT separately rather than presenting their difference as a true late-arrival metric.
