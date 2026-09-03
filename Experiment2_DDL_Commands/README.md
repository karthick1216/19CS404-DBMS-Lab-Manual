# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
<img width="1203" height="510" alt="image" src="https://github.com/user-attachments/assets/06aa8bc5-7551-4ae0-8f23-340d9a6d82e3" />


```sql
insert into Products(ProductID,Name,Category,Price,Stock)
VALUES(106,'Fitness Tracker','Wearables',NULL,NULL);
insert into Products(ProductID,Name,Category,Price,Stock)
VALUES(107,'Laptop','Electronic',999.99,50);
INSERT INTO ProductS(ProductID,Name,Category,Price,Stock)
VALUES(108,'Wireless Earbud','Accessorie',NULL,100);
```

**Output:**

<img width="1192" height="787" alt="image" src="https://github.com/user-attachments/assets/4d3c1356-5890-42f0-ab51-6f5503fdfad1" />


**Question 2**

<img width="1167" height="482" alt="image" src="https://github.com/user-attachments/assets/ecc1cc94-1240-4579-b9d0-2a584cbc4afc" />

```sql
insert into Books(ISBN,Title,Author,Publisher,Year)
VALUES('978-1234567890','Introduction to AI','John Doe',NULL,NULL);
insert into Books(ISBN,Title,Author,Publisher,Year)
VALUES('978-9876543210','Deep Learning','Jane Doe','TechPress',2022);
insert into Books(ISBN,Title,Author,Publisher,Year)
VALUES('978-1122334455','Cybersecurity Essentials','Alice Smith',NULL,2021);
```


**Output:**

<img width="1187" height="800" alt="image" src="https://github.com/user-attachments/assets/4df64e94-6cc5-4783-acdc-d67801cde615" />



**Question 3**
---
<img width="1222" height="448" alt="image" src="https://github.com/user-attachments/assets/7d189083-bdd2-4ef6-9f39-727515e986cf" />


```sql
CREATE TABLE Employees(
       EmployeeID integer primary key,
       FirstName NOT NULL,
       LASTName NOT NULL,
       Email UNIQUE,
       Salary integer check(salary>0),
       DepartmentID INT,
       FOREIGN KEY (DepartmentID) REFERENCes Departments(DepartmentID)
);
```

**Output:**

<img width="1260" height="783" alt="image" src="https://github.com/user-attachments/assets/ffacda48-1136-4525-a48b-4e1932f5fd93" />


**Question 4**
---
<img width="1265" height="240" alt="image" src="https://github.com/user-attachments/assets/84d94de7-52a4-44e9-8659-1626d8b8476b" />


```sql
create table jobs(
    job_id INT,
    job_title VARCHAR DEFAULT '',
    min_salary INT DEFAULT 8000,
    max_salary INT DEFAULT NULL
);
```

**Output:**

<img width="1275" height="767" alt="image" src="https://github.com/user-attachments/assets/8b079ee3-0638-4396-b885-32a8e8919bb3" />


**Question 5**
---
<img width="1130" height="387" alt="image" src="https://github.com/user-attachments/assets/77d4fc92-980d-4486-9608-af3746eb7f71" />


```sql
create table products(
     product_id INTEGER Primary key,
     product_name  TEXT NOT NULL,
     list_price DECIMAL(10,2) NOT NULL,
     discount DECIMAL(10,2) DEFAULT 0 NOT NULL,
     CONSTRAINT products check(
           list_price >= discount and
           discount >=0 and
           list_price>=0
     )
);

```

**Output:**

<img width="1263" height="727" alt="image" src="https://github.com/user-attachments/assets/48325337-c205-48dd-b0a8-8086481a3bab" />

**Question 6**
---
<img width="792" height="362" alt="image" src="https://github.com/user-attachments/assets/f2828b8c-1ed7-4c72-bf5f-e977743b237b" />




```sql
create table Reviews(
    ReviewID INTEGER,
    ProductID INTEGER,
    Rating REAL,
    ReviewText TEXT
);


```

**Output:**

<img width="1272" height="785" alt="image" src="https://github.com/user-attachments/assets/18df059d-5b5d-4f56-9fec-21c6cde1cc6d" />


**Question 7**
---
<img width="1185" height="298" alt="image" src="https://github.com/user-attachments/assets/e5bb0930-3969-4b3a-8164-75f7fd675371" />

```sql
create table Products(
   ProductID INTEGER,
   ProductName TEXT UNIQUE NOT NULL,
   Price REAL check(Price>0),
   StockQuantity INTEGER check(StockQuantity>0)
);
```

**Output:**

<img width="1258" height="682" alt="image" src="https://github.com/user-attachments/assets/1a87a63d-f86d-4594-93cb-e0c2dc364daf" />


**Question 8**
---
<img width="1022" height="306" alt="image" src="https://github.com/user-attachments/assets/b159fa3b-792e-46e4-b848-bfbb2ffa79b7" />


```sql
insert into Customers(CustomerID, Name, Address, Email)
SELECT CustomerID, Name, Address, Email
FROM Old_customers;


```

**Output:**

<img width="1280" height="812" alt="image" src="https://github.com/user-attachments/assets/3cf34744-1625-48ad-a117-f1ff858d588c" />


**Question 9**
---
<img width="1251" height="391" alt="image" src="https://github.com/user-attachments/assets/b7b2d734-b83e-422d-a319-9e8e23c94142" />


```sql
alter table employee ADD  department_id INTEGER;
ALTER table employee ADD  manager_id INTEGER DEFAULT NULL;

```

**Output:**
<img width="1305" height="780" alt="image" src="https://github.com/user-attachments/assets/6f66f3e7-e20c-46f2-8b4d-18ffaa6a2047" />



**Question 10**
---
<img width="1128" height="480" alt="image" src="https://github.com/user-attachments/assets/339cb449-9e02-4afd-b427-56b1e84265a5" />

```sql
alter table student_details ADD State TEXT;
```

**Output:**

<img width="1278" height="806" alt="image" src="https://github.com/user-attachments/assets/e02a3145-d4e9-4fd8-a54e-97f696ed0ea2" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
