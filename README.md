# 💽 Chinook Music Store – SQL Analysis Project

This project uses the [Chinook Database](https://github.com/lerocha/chinook-database) to explore real-world business insights for a digital music store. The dataset includes customers, invoices, artists, albums, and tracks, simulating a typical e-commerce environment for music sales.

---

## 🔍 Objectives

- Analyze sales performance by customer, genre, artist, and country
- Identify trends in monthly revenue
- Explore purchase behavior and product popularity

---

## 🛠 Tools Used

- **MySQL Workbench** (SQL queries)
- **Chinook Database** (`Chinook_MySql.sql`)
- **Excel/Tableau** (for optional data visualization)

---

## 📊 Sample Insights

### 1. Top 10 Spending Customers
```sql
SELECT
    FirstName, LastName, SUM(Total) AS TotalSpent
FROM customers
JOIN invoices ON customers.CustomerId = invoices.CustomerId
GROUP BY customers.CustomerId
ORDER BY TotalSpent DESC
LIMIT 10;

SELECT
    genres.Name, COUNT(*) AS TracksSold
FROM invoice_items
JOIN tracks ON invoice_items.TrackId = tracks.TrackId
JOIN genres ON tracks.GenreId = genres.GenreId
GROUP BY genres.Name
ORDER BY TracksSold DESC;

SELECT
    DATE_FORMAT(InvoiceDate, '%Y-%m') AS Month,
    ROUND(SUM(Total), 2) AS Revenue
FROM invoices
GROUP BY Month
ORDER BY Month;


/chinook-sql-analysis/
│
├── queries.sql           # Main SQL queries
├── visualizations.xlsx   # (Optional) Charts/graphs created in Excel
├── README.md             # Project documentation
└── Chinook_MySql.sql     # Database creation script


📝 Author Notes
I created this project to sharpen my SQL skills and build a portfolio of data analysis work. If you're a recruiter or hiring manager, feel free to reach out to learn more!

📬 Contact
LinkedIn: www.linkedin.com/in/veronica-hamani

Email: veronicahamani3@gmail.com


