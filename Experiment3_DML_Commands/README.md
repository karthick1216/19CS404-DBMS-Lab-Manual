# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
<img width="1182" height="485" alt="image" src="https://github.com/user-attachments/assets/9a2e8856-6674-4b28-9908-5b2df04d5301" />

```sql
select id,decimal, case when decimal>100 then 'High'
when decimal between 50 and 100 then 'Medium'
else 'Low'
end as category
from Calculations;
```

**Output:**
<img width="1240" height="807" alt="image" src="https://github.com/user-attachments/assets/61e5bf52-aca1-4c7a-aae8-533951163f01" />


**Question 2**
---
<img width="1267" height="752" alt="image" src="https://github.com/user-attachments/assets/b5abb611-c0a9-40fe-8066-9f1aa01f6fca" />

```sql
delete from Customer
where CUST_COUNTRY ='India' and CUST_CITY!='Chennai';
```

**Output:**

<img width="1280" height="816" alt="image" src="https://github.com/user-attachments/assets/5d67dd01-0fa8-4500-a47b-f9248c6d9c97" />


**Question 3**
---
<img width="996" height="445" alt="image" src="https://github.com/user-attachments/assets/bf2e17cf-d65a-4b4c-a767-c19baf910e46" />


```sql
select ContactName,Address,City
from customers
where Country IN ('Germany','Mexico','Spain');
```

**Output:**

<img width="1257" height="802" alt="image" src="https://github.com/user-attachments/assets/5e273bdd-2350-4eab-ae48-d352746ac9aa" />


**Question 4**
---
<img width="1057" height="308" alt="image" src="https://github.com/user-attachments/assets/8f93a2b9-7b83-46fe-ab4a-975fdc39c3c3" />


```sql
select name,commission
from salesman
limit 5;
```

**Output:**

<img width="1297" height="812" alt="image" src="https://github.com/user-attachments/assets/474656be-34ba-4ab1-876f-24ce2a555261" />


**Question 5**
---
<img width="745" height="386" alt="image" src="https://github.com/user-attachments/assets/4610ef54-ba5a-4e18-9959-d49b58f80033" />


```sql
delete from Doctors
where doctor_id between 2 and 4;


```

**Output:**

<img width="1246" height="805" alt="image" src="https://github.com/user-attachments/assets/c2f7ca5b-f8cd-4bc6-b806-b4eb00e304d1" />




**Question 6**
---
<img width="1061" height="382" alt="image" src="https://github.com/user-attachments/assets/c994b918-727d-47ba-8724-a4f1e72ec6b9" />

```sql
update Products
set reorder_lvl=20
where quantity<10 and category ='Snacks';
```

**Output:**

<img width="1250" height="807" alt="image" src="https://github.com/user-attachments/assets/7200cfa7-9093-45d2-ba48-6f8dffb0f503" />


**Question 7**
---
<img width="793" height="432" alt="image" src="https://github.com/user-attachments/assets/04660cb0-0cc2-419c-b45e-826ed82ce2af" />

```sql
select ename
from emp
where ename like 'S%' and LENGTH(ename)=5;
```

**Output:**

<img width="1263" height="728" alt="image" src="https://github.com/user-attachments/assets/64bd09a2-b21a-4b63-9e1c-1c58b762d7dc" />


**Question 8**
---
<img width="1252" height="367" alt="image" src="https://github.com/user-attachments/assets/4846e9b0-7318-4b08-8466-6d14cfd96e1e" />


```sql
delete from customer
where CUST_CITY!='New York' and OUTSTANDING_AMT>5000
```

**Output:**

<img width="1277" height="802" alt="image" src="https://github.com/user-attachments/assets/c6707ebd-71b4-43e6-b9e9-3fc35e01717a" />


**Question 9**
---
<img width="1107" height="470" alt="image" src="https://github.com/user-attachments/assets/53d9e946-cb51-4fd8-b92f-99c1413bee28" />

```sql
update PRODUCTS
set reorder_lvl=reorder_lvl*0.70
where product_name like '%cream%' and quantity>reorder_lvl;
```

**Output:**

<img width="1268" height="810" alt="image" src="https://github.com/user-attachments/assets/cfece701-64f1-4fc0-9b4e-640be6d96b4f" />

**Question 10**
---
<img width="1245" height="425" alt="image" src="https://github.com/user-attachments/assets/e6aa394b-2fda-40ad-83a3-1ff6865bbed8" />


```sql
delete from Customer
where CUST_NAME like '%Holmes%';
```

**Output:**

<img width="1272" height="792" alt="image" src="https://github.com/user-attachments/assets/9a28c16b-71fd-430c-8ded-c908f62f057e" />



## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
