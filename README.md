# OLA Performance Analytics Using SQL and Power BI

---

## 📌 Project Overview

This project analyzes OLA ride data to uncover operational inefficiencies, improve performance, and enhance customer satisfaction. By leveraging SQL for data exploration and Power BI for visualization, the analysis provides actionable insights to support data-driven business decisions.

---

## 🎯 Objectives

- Analyze booking trends, cancellation patterns, customer ratings, and revenue metrics.
- Identify operational inefficiencies affecting performance.
- Provide interactive dashboards using Power BI.
- Recommend strategies to reduce cancellations and improve service efficiency.

---

## 📂 Dataset

The dataset includes OLA ride information such as booking status, trip details, customer ratings, and revenue data.

- SQL Dataset : [Link](https://1drv.ms/x/c/408cf3a741dc6b18/ES0YeDisuBdJoORvH-eiN9gBZltNI7AlGfoLw2ASv-cn3w?e=gOVW6L)
- POWER BI Dataset : [Link](https://1drv.ms/x/c/408cf3a741dc6b18/ETTHONqVnXpIoLHCTvQ-CwMBRXGqkaHAo5sFtFxObV1CRg?e=WSPGbf)

---

## 🛠 Tools & Technologies Used

- SQL (MySQL)
- Power BI
- Excel / CSV Dataset

---

## 📊 Business Problems & SQL Solutions

### 1️⃣ Retrieve all successful bookings

```sql
SELECT *
FROM bookings
WHERE `Booking Status` = 'Successful';
```

---

### 2️⃣ Find the average ride distance for each vehicle type

```sql
SELECT `Vehicle Type`,
       AVG(`Ride Distance`) AS avg_distance
FROM bookings
GROUP BY `Vehicle Type`;
```

---

### 3️⃣ Get the total number of cancelled rides by customers

```sql
SELECT *
FROM bookings
WHERE `Cancelled Rides by Customer` = '1';
```

---

### 4️⃣ List the top 5 customers who booked the highest number of rides

```sql
SELECT `Customer ID`,
       COUNT(`Booking ID`) AS total_rides
FROM bookings
GROUP BY `Customer ID`
ORDER BY total_rides DESC
LIMIT 5;
```

---

### 5️⃣ Get rides cancelled by drivers due to personal & car-related issues

```sql
SELECT COUNT(*) AS total_driver_cancellations
FROM bookings
WHERE `Reason for cancelling by Driver` = 'Personal & Car related issues';
```

---

### 6️⃣ Find maximum and minimum driver ratings for Prime Sedan

```sql
SELECT MAX(`Driver Ratings`) AS max_rating,
       MIN(`Driver Ratings`) AS min_rating
FROM bookings
WHERE `Vehicle Type` = 'Prime Sedan';
```

---

### 7️⃣ Retrieve all rides where payment was made using UPI

```sql
SELECT *
FROM bookings
WHERE `Payment Method` = 'UPI';
```

---

### 8️⃣ Find average customer rating per vehicle type

```sql
SELECT `Vehicle Type`,
       AVG(`Customer Rating`) AS avg_customer_rating
FROM bookings
GROUP BY `Vehicle Type`;
```

---

### 9️⃣ Calculate total booking value of successfully completed rides

```sql
SELECT SUM(`Booking Value`) AS total_successful_booking_value
FROM bookings
WHERE `Booking Status` = 'Successful';
```

---

### 🔟 List incomplete rides with reasons

```sql
SELECT `Booking ID`,
       `Incomplete Rides Reason`
FROM bookings
WHERE `Booking Status` = 'Incomplete';
```

---

## 📈 Key Insights & Findings

- Majority of rides are completed successfully.
- Driver cancellations significantly impact operational efficiency.
- Revenue peaks during weekends and festive periods.
- Peak demand hours: **8–10 AM** and **5–8 PM**.
- Better driver availability correlates with higher customer ratings.

---

## 📌 Business Recommendations

- Reduce driver-side cancellations through performance monitoring.
- Implement surge pricing during peak hours.
- Introduce driver incentive programs.
- Improve dispatch optimization to reduce wait times.

---

## 🚀 Future Enhancements

- Integrate real-time ride data.
- Perform predictive analysis on cancellations.
- Competitor benchmarking for market positioning.
- Sentiment analysis on customer feedback.

---

