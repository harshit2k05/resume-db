# Resume Database Management System

A simple MySQL project that demonstrates basic database operations such as creating databases, tables, inserting records, retrieving data, and joining multiple tables.

## 📌 Features

- Create a MySQL database
- Create Users and Resumes tables
- Insert sample data
- Retrieve all records
- Search user by email
- Perform INNER JOIN between tables
- Beginner-friendly SQL project

---

## 🛠️ Technologies Used

- MySQL
- SQL

---

## 📂 Database Structure

### Users Table

| Column | Type |
|---------|------|
| id | INT (Primary Key, AUTO_INCREMENT) |
| name | VARCHAR(255) |
| email | VARCHAR(255) |

### Resumes Table

| Column | Type |
|---------|------|
| id | INT (Primary Key, AUTO_INCREMENT) |
| title | VARCHAR(255) |
| summary | TEXT |
| userId | INT (Foreign Key) |

---

## 📄 SQL Script

```sql
CREATE DATABASE resume_db;

USE resume_db;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL UNIQUE
);

INSERT INTO users (name, email)
VALUES
('Harshit', 'harshit@example.com'),
('Karan', 'karan@example.com'),
('Rahul', 'rahul@example.com');

CREATE TABLE resumes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    summary TEXT,
    userId INT,
    FOREIGN KEY (userId) REFERENCES users(id)
);

INSERT INTO resumes (title, summary, userId)
VALUES
('Full Stack Intern', 'Node, Express, MySQL', 1),
('QA Intern', 'Manual + API Testing', 2);
```

---

## ▶️ Queries Used

### Display All Users

```sql
SELECT * FROM users;
```

### Find User by Email

```sql
SELECT * FROM users
WHERE email='harshit@example.com';
```

### Display All Resumes

```sql
SELECT * FROM resumes;
```

### INNER JOIN

```sql
SELECT resumes.title, users.name
FROM resumes
JOIN users
ON resumes.userId = users.id;
```

---

# 📷 Project Screenshots

## Users Table

![Users Table](users_table.png)

---

## Search by Email

![Search User](search_user.png)

---

## Resumes Table

![Resumes Table](resumes_table.png)

---

## INNER JOIN Result

![Join Result](join_result.png)

---

## 📚 Learning Outcomes

- Database Creation
- Table Creation
- Primary Key
- Foreign Key
- AUTO_INCREMENT
- INSERT Query
- SELECT Query
- WHERE Clause
- INNER JOIN

---

## 👨‍💻 Author

**Harshit Joshi**

GitHub: https://github.com/harshit2k05

---

⭐ If you found this project useful, consider giving it a star!
