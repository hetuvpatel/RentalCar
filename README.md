# 🚗 Car Rental DBMS — Final Project

📄 **Report:** Final Report on Car Rental DBMS Design and Implementation  
🎓 **Course:** [CHY583 - Alternative Energies]  
👨‍💻 **Author:** Hetu Virajkumar Patel

---

## 📖 About the Project

The **Car Rental Database Management System (DBMS)** is designed to optimize operations for a car rental service, handling customer details, vehicle inventory, rental transactions, payments, and maintenance records.  
Built with a focus on **efficiency**, **security**, and **scalability**, the system ensures smooth management and reporting across all aspects of the rental business.

---

## ✨ Key Features

- 🧑‍🤝‍🧑 **Customer Management**: Personal details, licenses, and contact information.
- 🚗 **Vehicle Inventory Tracking**: Make, model, year, availability, and maintenance history.
- 🔗 **Rental Transactions Management**: Customer-car linking, rental dates, and statuses.
- 💳 **Payment Handling**: Payment records linked to rentals (amounts, dates, methods).
- 🛠️ **Maintenance Monitoring**: Service history tracking with costs.
- 🏢 **Branch/Location Management**: Tracking multiple branches and inventory distribution.

---

## 🛠️ Core Technologies

| Technology | Purpose |
|:------------|:--------|
| **SQL** | Database schema design, querying, and view creation |
| **Unix Shell Scripting** | Terminal-based database interaction and automation |
| **Normalization** | 3NF and BCNF compliance to ensure data integrity |
| **Views** | Aggregated reporting for rentals, payments, and maintenance |

---

## 🧩 Schema Design Overview

- **Customers** (`Customer_ID`, `License_Number`)
- **Cars** (`Car_ID`, `License_Plate`, `VIN`)
- **Rental_Transactions** (`Rental_ID`)
- **Payments** (`Payment_ID`)
- **Car_Maintenance** (`Maintenance_ID`)
- **Locations** (`Location_ID`)

All tables verified to comply with **Third Normal Form (3NF)** and **Boyce-Codd Normal Form (BCNF)**.

---

## 🧠 Normalization & Functional Dependencies

- Each table is fully normalized to **3NF** — no partial or transitive dependencies.
- **BCNF Verification** ensures every determinant is a candidate key (e.g., License Numbers, VINs).
- Redundant and inconsistent data is eliminated through strict normalization.

---

## 🔥 SQL Query Highlights

### Simple Queries:
```sql
-- List of Distinct Last Names of Customers
SELECT DISTINCT Last_Name FROM Customers ORDER BY Last_Name;

-- Count Available Cars by Make
SELECT Make, COUNT(*) AS NumberOfCars FROM Cars WHERE Availability_Status = 'Available' GROUP BY Make;

```
---

## Advanced Queries

-- Find Customers with No Active Rentals
SELECT First_Name, Last_Name
FROM Customers c
WHERE EXISTS (SELECT 1 FROM Rental_Transactions r WHERE r.Customer_ID = c.Customer_ID)
AND NOT EXISTS (SELECT 1 FROM Rental_Transactions r WHERE r.Customer_ID = c.Customer_ID AND r.Status = 'Active');

-- Average Maintenance Cost by Location
SELECT l.Location_Name, COUNT(cm.Maintenance_ID) AS Maintenance_Count, AVG(cm.Maintenance_Cost) AS Avg_Cost
FROM Locations l
JOIN Cars c ON l.Location_ID = c.Location_ID
JOIN Car_Maintenance cm ON c.Car_ID = cm.Car_ID
GROUP BY l.Location_Name;

---

## 🖥️ Application Implementation

- 📜 **Unix Shell Integration**: Menu-driven interface for interacting with the database via terminal.
- 🧩 **View Design**:
  - `Customer_Rental_Summary`
  - `Cars_Maintenance_View`
- 🛠️ **Operations Supported**:
  - Table creation, population, and querying
  - View generation and reporting

---

## ✅ Highlights & Achievements

- 📋 **Fully normalized database** (3NF and BCNF compliance).
- 🔥 **Advanced SQL queries** for powerful data insights.
- 💬 **Shell interface** for easy operations without a graphical UI.
- 🧹 **Clean and efficient schema**, reducing redundancy and ensuring data consistency.

---

## 📬 Contact

- **Portfolio:** [hetuvpatel.github.io/hetu-patel-portfolio](https://hetuvpatel.github.io/hetu-patel-portfolio)
- **Email:** [hetu.patel@torontomu.ca](mailto:hetu.patel@torontomu.ca)
- **GitHub:** [github.com/Patel-Hetu](https://github.com/Patel-Hetu)

---

> _"Driving efficient database management, one rental at a time!"_ 🚗💨

