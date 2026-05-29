Markdown
# 🛒 Supermarket Sales Data Analysis (SQL Project)

## 📌 Project Overview
Proyek ini bertujuan untuk menganalisis data transaksi mentah dari jaringan supermarket guna membantu CEO mengambil keputusan berbasis data (*data-driven decisions*) terkait performa cabang, profitabilitas produk, dan optimasi jadwal karyawan.

## 🛠️ Tech Stack & Database Schema
* **Database Management System:** MySQL
* **Tool:** MySQL Workbench
* **Key SQL Concepts Used:** Data Definition Language (DDL), Data Manipulation Language (DML), Aggregate Functions (`SUM`, `COUNT`), Grouping & Ordering (`GROUP BY`, `ORDER BY`), Date/Time Functions (`HOUR`).

## 📊 Business Problems & SQL Solutions

### 1. Cabang Performa Tertinggi (Branch Performance)
**Query:**
```sql
SELECT branch, city, SUM(total) AS total_revenue, SUM(gross_income) AS total_profit
FROM sales_data
GROUP BY branch, city
ORDER BY total_profit DESC;
Insight: Cabang B di kota Mandalay dan Cabang A di kota Yangon mendominasi total profitabilitas bisnis, sementara Cabang C masih memerlukan evaluasi strategi pemasaran lokal.

2. Analisis Profitabilitas Produk (Product Profitability)
Query:

SQL
SELECT product_line, SUM(quantity) AS total_qty_sold, SUM(gross_income) AS total_product_profit
FROM sales_data
GROUP BY product_line
ORDER BY total_product_profit DESC;
Insight: Kategori Health and beauty merupakan lini produk paling menguntungkan (Peringkat 1), sedangkan Electronic accessories memberikan kontribusi keuntungan terendah.

3. Optimasi Waktu Transaksi (Staffing & Hours Optimization)
Query:

SQL
SELECT HOUR(time) AS shopping_hour, COUNT(invoice_id) AS total_transactions
FROM sales_data
GROUP BY HOUR(time)
ORDER BY total_transactions DESC;
Insight: Transaksi tersebar merata sepanjang siang hingga sore hari (jam 10:00 - 17:00), menunjukkan stabilitas kunjungan pelanggan yang konsisten.
