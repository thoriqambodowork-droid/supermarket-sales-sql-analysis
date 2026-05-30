# 🛒 Supermarket Sales Data Analysis (SQL Project)

## 📌 Project Overview
This project aims to analyze raw transaction data from a supermarket chain to help the CEO make data-driven decisions regarding branch performance, product profitability, and employee schedule optimization.

## 🛠️ Tech Stack & Database Schema
* **Database Management System:** MySQL
* **Tool:** MySQL Workbench
* **Key SQL Concepts Used:** Data Definition Language (DDL), Data Manipulation Language (DML), Aggregate Functions (`SUM`, `COUNT`), Grouping & Ordering (`GROUP BY`, `ORDER BY`), Date/Time Functions (`HOUR`).

## 📊 Business Problems & SQL Solutions

### All SQL Queries
```sql
-- 1. Cabang Performa Tertinggi (Branch Performance)
SELECT branch, city, SUM(total) AS total_revenue, SUM(gross_income) AS total_profit
FROM sales_data
GROUP BY branch, city
ORDER BY total_profit DESC;

-- 2. Analisis Profitabilitas Produk (Product Profitability)
SELECT product_line, SUM(quantity) AS total_qty_sold, SUM(gross_income) AS total_product_profit
FROM sales_data
GROUP BY product_line
ORDER BY total_product_profit DESC;

-- 3. Optimasi Waktu Transaksi (Staffing & Hours Optimization)
SELECT HOUR(time) AS shopping_hour, COUNT(invoice_id) AS total_transactions
FROM sales_data
GROUP BY HOUR(time)
ORDER BY total_transactions DESC;
