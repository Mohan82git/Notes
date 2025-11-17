### **MySQL Roadmap (1.5 Months) – Focused on PHP & WordPress Development**

**Goal:** Master **MySQL** for **secure database management**, PHP-based **dynamic web applications**, and **WordPress development**.

---

## **Phase 1: MySQL Basics (1 Week)**

### **Topics to Cover**

✔ Introduction to Databases & MySQL  
✔ MySQL Installation & Setup  
✔ Basic Commands (`SHOW DATABASES`, `USE database_name`, `SHOW TABLES`)  
✔ Creating Databases & Tables (`CREATE DATABASE`, `CREATE TABLE`)  
✔ Data Types (`INT`, `VARCHAR`, `TEXT`, `DATE`, `BOOLEAN`)

### **Hands-on Tasks**

✅ Create a **database named `mydb`**  
✅ Define a **`users` table** with `id`, `name`, `email`, `password`, `created_at`  
✅ Insert **5 dummy users** into the `users` table

### **Common Mistakes to Avoid**

❌ Using **wrong data types** (`VARCHAR(255)` for numbers instead of `INT`)  
❌ Not setting **primary keys (`id INT AUTO_INCREMENT PRIMARY KEY`)**  
❌ Forgetting to use **`NOT NULL` for required fields**

---

## **Phase 2: CRUD Operations (1 Week)**

### **Topics to Cover**

✔ `INSERT`, `SELECT`, `UPDATE`, `DELETE`  
✔ Filtering with `WHERE` (`WHERE email = 'example@gmail.com'`)  
✔ Sorting (`ORDER BY column ASC|DESC`)  
✔ Limiting Results (`LIMIT 5`)

### **Hands-on Tasks**

✅ Insert **a new user** into the `users` table  
✅ Update **a user's email**  
✅ Delete **a user based on their ID**  
✅ Fetch **users with names starting with 'A'**

### **Common Mistakes to Avoid**

❌ Using `DELETE FROM table;` (Removes all data without a condition)  
❌ Forgetting **`WHERE` in `UPDATE` or `DELETE`** (Affects all rows)  
❌ Using `SELECT *` instead of selecting only necessary columns

---

## **Phase 3: Relationships & Joins (1 Week)**

### **Topics to Cover**

✔ One-to-One, One-to-Many, Many-to-Many Relationships  
✔ Foreign Keys (`FOREIGN KEY (user_id) REFERENCES users(id)`)  
✔ `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`  
✔ `GROUP BY`, `HAVING`

### **Hands-on Tasks**

✅ Create a **`posts` table** (`id`, `user_id`, `title`, `content`)  
✅ Link posts to users using **foreign keys**  
✅ Fetch all **users with their posts** using `INNER JOIN`  
✅ Find **users who have more than 2 posts** using `GROUP BY`

### **Common Mistakes to Avoid**

❌ Not **defining foreign keys** (Leads to data inconsistency)  
❌ Using `INNER JOIN` when `LEFT JOIN` is needed (Losing unmatched data)  
❌ Forgetting to **index foreign keys** (Slows down queries)

---

## **Phase 4: Advanced Queries (1 Week)**

### **Topics to Cover**

✔ `UNION` & `UNION ALL` (Combining results from multiple queries)  
✔ `CASE` Statements (Conditional Logic)  
✔ Subqueries (`SELECT * FROM users WHERE id IN (SELECT user_id FROM posts)`)  
✔ Full-Text Search (`MATCH(column) AGAINST('keyword')`)

### **Hands-on Tasks**

✅ Find **users who have not posted anything**  
✅ Search for a **post using keywords**  
✅ Rank **users based on the number of posts**

### **Common Mistakes to Avoid**

❌ Using **subqueries instead of JOINs** (Slower performance)  
❌ Not adding **indexes on searchable columns**  
❌ Forgetting to use **`DISTINCT` to remove duplicate results**

---

## **Phase 5: Security & Optimization (1 Week)**

### **Topics to Cover**

✔ Preventing SQL Injection (`Prepared Statements`)  
✔ Indexing (`CREATE INDEX index_name ON table(column)`)  
✔ Transactions (`START TRANSACTION`, `COMMIT`, `ROLLBACK`)  
✔ MySQL Performance Tuning (`EXPLAIN`, `ANALYZE`)

### **Hands-on Tasks**

✅ Optimize **slow queries using indexes**  
✅ Implement **prepared statements in PHP**  
✅ Use **transactions in a banking system example**

### **Common Mistakes to Avoid**

❌ Not using **prepared statements** (Leads to SQL injection attacks)  
❌ Overusing **indexes** (Slows down inserts/updates)  
❌ Forgetting to **use transactions for multi-step operations**

---

## **Final Project: MySQL-Powered Web App (2 Weeks)**

✅ **Choose one:**  
1️⃣ **User Management System** (User roles, profile updates)  
2️⃣ **Blogging Platform** (Users, posts, comments)  
3️⃣ **E-Commerce Backend** (Products, orders, customers)

---

### **Final Checklist for MySQL Mastery**

✔ **Database Design:** Tables, relationships, foreign keys  
✔ **CRUD Operations:** `INSERT`, `SELECT`, `UPDATE`, `DELETE`  
✔ **Joins & Relationships:** `INNER JOIN`, `LEFT JOIN`, `GROUP BY`  
✔ **Performance Optimization:** Indexing, transactions, tuning  
✔ **Security:** Prevent SQL injection, enforce constraints  
✔ **Complete Project:** A real-world MySQL-backed application

This **MySQL roadmap** ensures you're **job-ready** for PHP, WordPress, and rtCamp. Let me know if you need **custom queries or debugging help!**