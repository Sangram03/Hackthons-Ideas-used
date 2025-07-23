## 📚 Categories of MySQL Commands

1. **Database commands**
2. **Table commands**
3. **Data Manipulation commands (CRUD)**
4. **Query commands**
5. **User and Access control**
6. **Joins and advanced clauses**

---

## 1️⃣ Database Commands

| Command           | Description                     | Example                 |
| ----------------- | ------------------------------- | ----------------------- |
| `CREATE DATABASE` | Creates a new database          | `CREATE DATABASE mydb;` |
| `SHOW DATABASES`  | Lists all databases             | `SHOW DATABASES;`       |
| `USE`             | Selects a database to work with | `USE mydb;`             |
| `DROP DATABASE`   | Deletes a database              | `DROP DATABASE mydb;`   |

---

## 2️⃣ Table Commands

| Command              | Description                | Example             |
| -------------------- | -------------------------- | ------------------- |
| `CREATE TABLE`       | Creates a new table        | See below 👇        |
| `DESCRIBE` or `DESC` | Shows table structure      | `DESC users;`       |
| `SHOW TABLES`        | Lists tables in current DB | `SHOW TABLES;`      |
| `DROP TABLE`         | Deletes a table            | `DROP TABLE users;` |
| `ALTER TABLE`        | Modifies table structure   | See below 👇        |

### ✅ Create Table Example:

```sql
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100),
  email VARCHAR(100),
  age INT
);
```

### ✅ Alter Table:

```sql
ALTER TABLE users ADD phone VARCHAR(15);         -- Add column
ALTER TABLE users MODIFY age TINYINT;            -- Change type
ALTER TABLE users DROP COLUMN phone;             -- Drop column
```

---

## 3️⃣ Data Manipulation (CRUD)

| Operation  | Command       | Example                                                            |
| ---------- | ------------- | ------------------------------------------------------------------ |
| **Create** | `INSERT INTO` | `INSERT INTO users (name, email) VALUES ('Sam', 'sam@gmail.com');` |
| **Read**   | `SELECT`      | `SELECT * FROM users;`                                             |
| **Update** | `UPDATE`      | `UPDATE users SET name='Sangram' WHERE id=1;`                      |
| **Delete** | `DELETE`      | `DELETE FROM users WHERE id=1;`                                    |

---

## 4️⃣ Query Clauses

| Clause     | Use                      | Example                                            |
| ---------- | ------------------------ | -------------------------------------------------- |
| `WHERE`    | Filters rows             | `SELECT * FROM users WHERE age > 18;`              |
| `ORDER BY` | Sorts results            | `SELECT * FROM users ORDER BY age DESC;`           |
| `LIMIT`    | Restricts number of rows | `SELECT * FROM users LIMIT 5;`                     |
| `LIKE`     | Pattern matching         | `SELECT * FROM users WHERE name LIKE 'S%';`        |
| `IN`       | Matches multiple values  | `SELECT * FROM users WHERE id IN (1, 2, 3);`       |
| `BETWEEN`  | Matches a range          | `SELECT * FROM users WHERE age BETWEEN 18 AND 25;` |

---

## 5️⃣ Joins (Combining Tables)

### 👇 Types of JOINs:

| Join Type     | Description                         | Example                                                               |
| ------------- | ----------------------------------- | --------------------------------------------------------------------- |
| `INNER JOIN`  | Only matching rows from both tables | `SELECT * FROM orders INNER JOIN users ON orders.user_id = users.id;` |
| `LEFT JOIN`   | All from left + matching from right | `SELECT * FROM users LEFT JOIN orders ON users.id = orders.user_id;`  |
| `RIGHT JOIN`  | All from right + matching from left | `SELECT * FROM orders RIGHT JOIN users ON orders.user_id = users.id;` |
| `FULL JOIN`\* | All rows from both sides            | Not directly supported in MySQL – use `UNION`                         |

---

## 6️⃣ Aggregate Functions

| Function   | Use                         | Example                                         |
| ---------- | --------------------------- | ----------------------------------------------- |
| `COUNT()`  | Counts rows                 | `SELECT COUNT(*) FROM users;`                   |
| `SUM()`    | Sums a column               | `SELECT SUM(age) FROM users;`                   |
| `AVG()`    | Average of values           | `SELECT AVG(age) FROM users;`                   |
| `MAX()`    | Maximum value               | `SELECT MAX(age) FROM users;`                   |
| `MIN()`    | Minimum value               | `SELECT MIN(age) FROM users;`                   |
| `GROUP BY` | Groups rows for aggregation | `SELECT age, COUNT(*) FROM users GROUP BY age;` |

---

## 7️⃣ User & Access Management

| Command       | Description        | Example                                                   |
| ------------- | ------------------ | --------------------------------------------------------- |
| `CREATE USER` | Adds a new user    | `CREATE USER 'sam'@'localhost' IDENTIFIED BY 'password';` |
| `GRANT`       | Gives privileges   | `GRANT ALL ON mydb.* TO 'sam'@'localhost';`               |
| `REVOKE`      | Removes privileges | `REVOKE ALL ON mydb.* FROM 'sam'@'localhost';`            |
| `DROP USER`   | Deletes a user     | `DROP USER 'sam'@'localhost';`                            |

---

## 🧪 Useful Tips

* Always use `WHERE` with `DELETE` and `UPDATE` to avoid affecting all rows.
* Use `LIMIT` while testing queries.
* Use `SHOW WARNINGS;` after queries to debug issues.
* MySQL is **case-insensitive** for most commands and table names (depends on OS).
* Use `EXPLAIN` to analyze query performance.

---

## ✅ Example Project Schema

```sql
CREATE TABLE products (
  id INT PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(255),
  price DECIMAL(10,2),
  stock INT
);

CREATE TABLE orders (
  id INT AUTO_INCREMENT PRIMARY KEY,
  user_id INT,
  product_id INT,
  quantity INT,
  order_date DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

---

