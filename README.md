# 🍕 Pizza Sales Analysis

**Author**: Anushree Jindal <br>
**Dataset Used**: 

## 🛠️ Tools Used
- MySQL  

## 📌 Objective

This project aims to analyze the transactional sales data of a pizza store using SQL to uncover meaningful business insights. The analysis evaluates sales performance, customer ordering patterns, revenue generation, product popularity, and category-wise trends using SQL concepts such as joins, aggregate functions, subqueries, CTEs, and window functions.

## 🧾 Understanding the Dataset
This dataset consists of four relational tables that store the transactional sales data of the pizza store along with information about the variety of pizzas it offers.

### 1. Orders
This table stores information about each customer order and serves as the parent table for all transactions.

| Column | Data Type | Description |
| :------ | :-------- | :---------- |
| **order_id** | `INT` | Unique identifier for each order (**Primary Key**). |
| **order_date** | `DATE` | Date on which the order was placed. |
| **order_time** | `TIME` | Time at which the order was placed, useful for analyzing hourly order trends. |

---

### 2. Order_Details
This table contains the line-item details of every order, with each record representing a specific pizza ordered.

| Column | Data Type | Description |
| :------ | :-------- | :---------- |
| **order_details_id** | `INT` | Unique identifier for each order detail (**Primary Key**). |
| **order_id** | `INT` | References the corresponding order in the **Orders** table (**Foreign Key**). |
| **pizza_id** | `VARCHAR` | References the pizza ordered from the **Pizzas** table (**Foreign Key**). |
| **quantity** | `INT` | Number of units of the selected pizza ordered. |

---

### 3. Pizzas
This table stores information about the individual pizza variants available for sale, including their size and price.

| Column | Data Type | Description |
| :------ | :-------- | :---------- |
| **pizza_id** | `VARCHAR` | Unique identifier for each pizza variant (**Primary Key**). |
| **pizza_type_id** | `VARCHAR` | References the corresponding pizza type in the **Pizza_Types** table (**Foreign Key**). |
| **size** | `VARCHAR` | Size of the pizza (S, M, L, XL, XXL). |
| **price** | `DECIMAL` | Selling price of the pizza. |

---

### 4. Pizza_Types
This table contains descriptive information about each pizza type and its ingredients.

| Column | Data Type | Description |
| :------ | :-------- | :---------- |
| **pizza_type_id** | `VARCHAR` | Unique identifier for each pizza type (**Primary Key**). |
| **name** | `VARCHAR` | Name of the pizza. |
| **category** | `VARCHAR` | Pizza category (Classic, Chicken, Supreme, Veggie, etc.). |
| **ingredients** | `TEXT` | List of ingredients used in the pizza. |
