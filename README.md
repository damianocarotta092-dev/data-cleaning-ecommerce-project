# 🧹 Data Cleaning - E-commerce Dataset

## 📌 Project Overview

This project demonstrates the process of cleaning and preprocessing a messy e-commerce dataset using Python and Pandas.

The dataset contains common real-world data issues such as:

* Missing values
* Inconsistent formatting
* Invalid entries
* Mixed data types

The goal of this project is to transform raw, unstructured data into a clean and analysis-ready dataset.

---

## ⚙️ Technologies Used

* Python
* Pandas
* Google Colab

---

## 🧠 Data Cleaning Process

The following steps were applied:

### 1. Duplicate Removal

* Removed duplicate rows based on `order_id`

### 2. Customer Name Cleaning

* Standardized text formatting (capitalization and spacing)

### 3. Email Validation

* Invalid email formats replaced with `NaN`
* Standardized all emails to lowercase

### 4. Country Standardization

* Unified all variations (e.g. "ITALIA", "it", "italy") into "Italy"

### 5. Date Cleaning

* Handled multiple date formats
* Created a clean datetime column (`order_date`)
* Converted values to proper datetime format

### 6. Revenue Cleaning

* Removed currency symbols (€)
* Converted values to numeric format
* Invalid values replaced with `NaN`

### 7. Age Cleaning

* Removed unrealistic values (e.g. age > 100)
* Handled missing values
* Converted to integer type

---

## 📊 Final Dataset

The cleaned dataset is structured and ready for analysis with consistent formats and correct data types.

Columns:

* `order_id`
* `customer_name`
* `email`
* `country`
* `order_date`
* `revenue_eur`
* `age`

---

## 🔄 Before vs After

### ❌ Messy Dataset

```
order_id | customer_name | email           | country | order_date   | revenue        | age
1001     | Mario Rossi   | mario@gmail.com | Italy   | 12/01/2025   | €120           | 32
1002     | maria rossi   | MARIA@gmail.com | ITALIA  | 2025-01-13   | 89€            | NaN
1003     | Luca Bianchi  | luca@gmail      | Italia  | Jan 14 2025  | one hundred    | 29
1004     | Anna Verdi    | anna@gmail.com  | italy   | 14-01-25     | €250           | 150
```

---

### ✅ Cleaned Dataset

```
order_id | customer_name | email            | country | order_date  | revenue_eur | age
1001     | Mario Rossi   | mario@gmail.com  | Italy   | 2025-01-12  | 120         | 32
1002     | Maria Rossi   | maria@gmail.com  | Italy   | 2025-01-13  | 89          | <NA>
1003     | Luca Bianchi  | NaN              | Italy   | 2025-01-14  | NaN         | 29
1004     | Anna Verdi    | anna@gmail.com   | Italy   | 2025-01-14  | 250         | <NA>
```

---

## 📁 Repository Structure

```
data-cleaning-ecommerce/
│── messy_ecommerce_dataset.csv
│── cleaned_ecommerce_dataset.csv
│── Dataset_Cleaning_01.ipynb
│── README.md
```

---

## 🚀 Key Takeaways

* Real-world datasets are often messy and inconsistent
* Data cleaning is a critical step before analysis
* Small inconsistencies can significantly impact results
* Clear and structured data improves reliability and usability

---

## 📊 Full Dataset Comparison

### 🟥 messy_dataset

```
order_id	customer_name	email	country	order_date	revenue	age
1001	Mario Rossi	mario@gmail.com	Italy	12/01/2025	€120	32
1002	maria rossi	MARIA@gmail.com	ITALIA	2025-01-13	89€	NaN
1003	Luca Bianchi	luca@gmail	Italia	Jan 14 2025	one hundred	29
1004	Anna Verdi	anna@gmail.com	italy	14-01-25	€250	150
1006	Giulia Neri	giulia@gmail.com	Italy	2025/01/15	€200	27
1007	Marco Blu	marco@gmail.com	Italya	15 Jan 2025	300€	40
1008	Sara Gialli	sara@gmail	ITALY	2025.01.16	€180	NaN
1009	Paolo Rosa	paolo@gmail.com	IT	NaN	€90	35
```

---

### 🟩 cleaned_dataset

```
order_id	customer_name	email	country	order_date	revenue_eur	age
1001	Mario Rossi	mario@gmail.com	Italy	2025-01-12	120	32
1002	Maria Rossi	maria@gmail.com	Italy	2025-01-13	89	<NA>
1003	Luca Bianchi	NaN	Italy	2025-01-14	NaN	29
1004	Anna Verdi	anna@gmail.com	Italy	2025-01-14	250	<NA>
1006	Giulia Neri	giulia@gmail.com	Italy	2025-01-15	200	27
1007	Marco Blu	marco@gmail.com	Italy	2025-01-15	300	40
1008	Sara Gialli	NaN	Italy	2025-01-16	180	<NA>
1009	Paolo Rosa	paolo@gmail.com	Italy	NaT	90	35
```
