# Drug Inventory Management System

### Python-Based Inventory Analysis and Decision-Support Prototype

A Python-based Drug Inventory Management System developed as an educational/portfolio project to analyse simulated medicine inventory data, identify stock-level and expiry risks, calculate inventory value, and provide management-focused insights.

---

##  Project Overview

Medicine inventory management requires timely information about stock availability, inventory value, expiry risk, and potential overstocking.

This project demonstrates how Python can transform structured inventory records into useful information that can support inventory-management decisions.

The project follows this workflow:

**Data → Validation → Processing → Analysis → Risk Identification → Management Summary → Stakeholder Action**

> **Note:** This project uses a simulated inventory dataset and is intended as an educational prototype. It is not a replacement for professional pharmaceutical inventory-management systems.

---

##  Project Objectives

The system was developed to answer practical inventory-management questions such as:

* How many medicines are being tracked?
* What is the total inventory value?
* Which medicines are low stock?
* Which medicines are critically low?
* Which medicines are overstocked?
* Which medicine has the highest inventory value?
* Which medicine has the lowest stock?
* How is inventory distributed across facilities?
* Which medicines are approaching expiry?
* Which inventory issues require management attention?
* What actions can stakeholders consider based on the findings?

---

##  Dataset

The project uses a **simulated medicine inventory dataset** created directly in Python.

Each inventory record contains:

* Drug ID
* Drug Name
* Category
* Facility
* Quantity
* Reorder Level
* Maximum Stock
* Unit Price
* Supplier
* Expiry Date

### Data Quality

The original dataset contained:

* **28 total records**
* **25 valid records**
* **3 invalid records**

The validation process identified issues including:

* Negative quantity
* Negative unit price
* Maximum stock below reorder level
* Missing medicine name

Invalid records were excluded from the subsequent inventory analysis.

---

##  Technologies Used

* **Python 3**
* Python data structures
* Functions
* Conditional statements
* Loops
* Lists and dictionaries
* Date handling with `datetime`
* Input/output
* Data validation
* Inventory analysis

---

##  Key Features

### 1. Data Validation

The system checks inventory records before analysis to identify data-quality problems.

Validation rules include:

* Negative quantities
* Negative unit prices
* Missing medicine names
* Maximum stock below reorder level

---

### 2. Inventory Value Analysis

Inventory value is calculated using:

```text
Inventory Value = Quantity × Unit Price
```

The system calculates individual medicine values as well as total inventory value.

**Total inventory value:** ₦2,009,950

---

### 3. Stock Classification

Medicines are classified using the following rules:

| Status    | Rule                               |
| --------- | ---------------------------------- |
| Critical  | Quantity ≤ 50% of Reorder Level    |
| Low Stock | Quantity ≤ Reorder Level           |
| Overstock | Quantity > Maximum Stock           |
| Adequate  | Does not meet the conditions above |

### Stock Summary

| Stock Status | Number of Medicines |
| ------------ | ------------------: |
| Critical     |                   4 |
| Low Stock    |                   5 |
| Adequate     |                  13 |
| Overstock    |                   3 |

The notebook also identifies **9 medicines at or below their reorder level**.

---

### 4. Reorder Analysis

For medicines classified as Critical or Low Stock, the system calculates:

```text
Reorder Quantity = Maximum Stock − Current Quantity
```

The analysis identified **9 medicines requiring replenishment attention**.

---

### 5. Highest-Value Medicine

The highest-value medicine in the validated dataset was:

**DRG003 — Artemether/Lumefantrine**

* Quantity: 850 units
* Unit Price: ₦450
* Inventory Value: ₦382,500

---

### 6. Lowest-Stock Medicine

The lowest-stock medicine was:

**DRG017 — ORS Sachets**

* Quantity: 40 units
* Reorder Level: 200 units
* Stock Status: Critical

---

### 7. Facility Analysis

The validated inventory records are distributed across **12 healthcare facilities**.

* Lagos General Hospital: 3 records
* The other 11 facilities: 2 records each

This accounts for all **25 valid inventory records**.

---

### 8. Low Stock + High Unit Price

The system compares medicine unit prices against the average unit price of:

**₦439.60**

Three medicines were identified as both low stock and above this average:

| Drug                  | Quantity | Unit Price |
| --------------------- | -------: | ---------: |
| Insulin               |       45 |     ₦3,500 |
| Ceftriaxone Injection |       60 |       ₦900 |
| Salbutamol Inhaler    |       85 |     ₦1,200 |

---

### 9. Expiry Risk Analysis

The project uses a **30-day threshold** to define near-expiry medicines.

The analysis identified **4 medicines** that were both low stock and near expiry:

| Drug                  | Quantity | Days to Expiry |
| --------------------- | -------: | -------------: |
| ORS Sachets           |       75 |             29 |
| Insulin               |       45 |             15 |
| Ceftriaxone Injection |       60 |              9 |
| ORS Sachets           |       40 |              4 |

The analysis date used in the notebook was **September 16, 2026**.

---

##  Interactive Management System

The project goes beyond individual calculations by connecting the reusable functions to an interactive menu.

### Available Menu Options

```text
1. View Inventory
2. Search Medicine
3. View Low-Stock Medicines
4. View Critical-Stock Medicines
5. View Overstocked Medicines
6. View Near-Expiry Medicines
7. View Inventory Summary
8. Exit
```

The program continues running until the user selects the Exit option.

It also handles invalid menu selections.

---

##  Reusable Python Functions

The project was structured using reusable functions including:

```python
calculate_inventory_value()
classify_stock()
view_inventory()
search_medicine()
get_low_stock_medicines()
get_critical_stock_medicines()
get_overstocked_medicines()
get_near_expiry_medicines()
display_inventory_summary()
display_menu()
```

This helped make the system more organized, reusable, and easier to maintain.

---

##  Key Project Findings

The analysis produced several important inventory-management indicators:

* **25** valid inventory records
* **28** total records before validation
* **3** invalid records
* **12** healthcare facilities
* **7,890** total inventory units
* **₦2,009,950** total inventory value
* **₦439.60** average unit price
* **₦80,398** average inventory value
* **9** low-stock medicines
* **4** critical-stock medicines
* **3** overstocked medicines
* **4** near-expiry medicines
* **₦382,500** highest individual inventory value

---

##  Stakeholder Insights

Based on the analysis, the project identifies areas that may require management attention.

### Pharmacy & Inventory Managers

* Monitor low-stock and critical-stock medicines.
* Review medicines approaching expiry.
* Monitor overstocked medicines.
* Apply appropriate inventory-control and stock-rotation practices.

### Procurement Officers

* Review critical and low-stock medicines when planning replenishment.
* Avoid unnecessary procurement of already overstocked medicines.
* Consider current inventory levels when making purchasing decisions.

### Facility Managers

* Monitor inventory positions within their facilities.
* Coordinate with pharmacy and procurement teams when shortages or excess stock are identified.
* Support appropriate redistribution where necessary and permitted.

### Health-System Decision-Makers

* Use inventory summaries to identify supply-management issues.
* Support coordinated procurement and distribution decisions.
* Encourage regular monitoring of stock levels, expiry dates, and inventory value.

---

## 🎓 What We Learned

Through this project, we applied Python to a practical inventory-management scenario and strengthened our understanding of:

* Data validation
* Lists and dictionaries
* Loops and conditional logic
* Functions and reusable code
* Inventory calculations
* Date calculations
* Stock classification
* Risk identification
* Interactive console applications
* Translating analytical results into practical management insights

---

##  Future Improvements

Possible future improvements include:

* Connecting the system to a real database
* Adding a graphical user interface
* Adding data visualizations and dashboards
* Importing inventory data from CSV/Excel files
* Adding automated reporting
* Adding user authentication
* Adding automated stock alerts
* Adding more advanced demand and consumption analysis

---
##  Disclaimer

This project uses a **simulated inventory dataset** and is intended for educational and portfolio purposes.

The analytical thresholds used in the project are simplified assumptions. Real-world pharmaceutical inventory decisions should also consider demand, consumption rates, procurement lead times, budgets, clinical requirements, professional judgement, and applicable inventory-management procedures.

---

##  Project Team

**Team Project**

Developed collaboratively as part of a hands-on Python/inventory-management project.

---

##  Project Structure

```text
drug-inventory-management-system/
│
├── drug_inventory_management.ipynb
├── README.md
└── .gitignore
```

---

##  Project Status

**Completed — Educational / Portfolio Prototype**
