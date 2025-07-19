# 🧾 Billing System - Java Swing + MySQL

This project is a **Java Swing-based Billing System** that allows users to:
- Enter buyer details
- Select products using Product ID
- Add items to a bill with quantity & auto-calculated pricing
- Automatically calculate subtotal and final total
- Save all billing data into a MySQL database (buyers, transactions, transaction items)
- Export the bill to a PDF file
- Print the bill directly

---

## 📌 Features

- 🛒 Add products to bill via Product ID
- 🔢 Auto calculation of total price
- 📥 Subtotal & Final Total computation
- 🧾 Generate professional PDF bill using iText
- 🖨️ Print directly from the application
- 💾 Save buyer & transaction data to MySQL
- 🎯 Clean UI with Swing components

---

## 🛠️ Technologies Used

| Tech            | Description                       |
|-----------------|-----------------------------------|
| Java (JDK 24)   | Core application using Swing      |
| MySQL           | Backend database                  |
| JDBC            | Database connectivity             |
| iText PDF       | For exporting the bill to PDF     |
| NetBeans        | IDE used for UI and development   |
| Maven           | Dependency and build management   |

---

## 🧮 Database Schema

### 📂 Tables Used:

#### 1. `products`
```sql
CREATE TABLE products (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    price DOUBLE
);
```
#### 2.buyers

```sql
CREATE TABLE buyers (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    address VARCHAR(255),
    contact_number VARCHAR(20),
    email VARCHAR(100)
);
```
#### 3. transactions
```sql
CREATE TABLE transactions (
    transaction_id INT PRIMARY KEY AUTO_INCREMENT,
    buyer_id INT,
    transaction_date DATE,
    payment_method VARCHAR(50),
    FOREIGN KEY (buyer_id) REFERENCES buyers(id)
);
```
#### 4. transaction_items
```sql
CREATE TABLE transaction_items (
    id INT PRIMARY KEY AUTO_INCREMENT,
    transaction_id INT,
    product_id INT,
    quantity INT,
    unit_price DOUBLE,
    total_price DOUBLE,
    FOREIGN KEY (transaction_id) REFERENCES transactions(transaction_id),
    FOREIGN KEY (product_id) REFERENCES products(id)
);
```



## 🚀 How to Run

1.Clone the repository:

```sql
git clone https://github.com/shivakasula48/-Generating-the-Bill.git
cd Generating-the-Bill
```

2.Import the project into NetBeans or run with Maven.

3.Make sure MySQL is running and the database testdb is created.

4.Set up the tables above in testdb.

5.Run the application:

``` mathematica

Right-click → Run
```
