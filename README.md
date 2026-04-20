# 📈 Financial Portfolio Management System (SQL)

Ye ek DBMS project hai jo users ke financial assets, investments, aur transactions ko manage aur track karne ke liye design kiya gaya hai.

## 🚀 Features
* **Database Setup:** Automatic database aur table creation logic (`IF NOT EXISTS`).
* **Portfolio Tracking:** User-wise portfolio management.
* **Asset Categorization:** Stocks, Commodities, aur baaki assets ka detailed record.
* **Investment Logs:** Quantity aur purchase price ke saath investment tracking.
* **Transaction History:** Saari buy/sell activities ka chronological record.

## 📊 Database Schema (ER Diagram)
Project ka structure niche diye gaye tables par based hai:
* `portfolio`: User ki basic details aur total value.
* `asset`: Assets ki market price aur type.
* `investment`: Portfolio aur Assets ka link (Relationship table).
* `transaction`: Har transaction ka audit trail.



## 🛠️ Tech Stack
* **Language:** SQL (Structured Query Language)
* **Database:** MySQL
* **Tools:** MySQL Workbench, GitHub Codespaces

## ⚙️ How to Use
1. Is repository ko clone karein ya `Mainportfolio_db.sql` file download karein.
2. Apne MySQL Workbench mein file ko open karein.
3. Poore script ko select karke `Execute` (Lightning icon) par click karein.
4. Tables aur Sample data automatically populate ho jayenge.

## 📝 Sample Queries
Data check karne ke liye aap ye commands use kar sakte hain:
```sql
-- Saare assets dekhne ke liye
SELECT * FROM asset;

-- User ka total portfolio value check karne ke liye
SELECT user_name, total_value FROM portfolio;
