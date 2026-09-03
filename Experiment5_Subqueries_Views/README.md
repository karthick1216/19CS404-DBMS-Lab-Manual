# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
<img width="865" height="477" alt="image" src="https://github.com/user-attachments/assets/2a860c68-3a94-4348-b483-7b345e02f527" />

```sql
Select *
from CUSTOMERs
where ADDRESS='Delhi';
```

**Output:**

Select *
from CUSTOMERs
where ADDRESS='Delhi';

**Question 2**
---
<img width="1128" height="543" alt="image" src="https://github.com/user-attachments/assets/4767e493-2a98-4ace-9355-81676da5a1f4" />

```sql
select salesman_id, name
from salesman
where salesman_id in (select salesman_id from customer group by salesman_id having count(customer_id)>1) ;


```

**Output:**

<img width="1270" height="727" alt="image" src="https://github.com/user-attachments/assets/8d40f558-b868-4442-aa4c-311c872e3a7d" />


**Question 3**
---
<img width="860" height="492" alt="image" src="https://github.com/user-attachments/assets/f4f24b05-7e62-4081-9a68-9fa13e2e69ff" />


```sql
select *
from CUSTOMERS
where SALARY>4500
```

**Output:**

select *
from CUSTOMERS
where SALARY>4500

**Question 4**
---
<img width="880" height="485" alt="image" src="https://github.com/user-attachments/assets/046f75f7-5ee1-47fe-8464-39fca9b6dc7b" />


```sql
select *
from CUSTOMERS
where ADDRESS='Delhi' and AGE<30
order by id asc;
```

**Output:**

<img width="1325" height="767" alt="image" src="https://github.com/user-attachments/assets/a40ecef5-064d-4d2c-875c-47190762e796" />


**Question 5**
---
<img width="915" height="481" alt="image" src="https://github.com/user-attachments/assets/2c86bf8d-7072-4a07-a6e7-bd8e036dc3ce" />


```sql
select *
from CUSTOMERS
where SALARY =1500;
```

**Output:**

<img width="1302" height="752" alt="image" src="https://github.com/user-attachments/assets/1913aae2-ece0-4a10-97d4-5a63db2e2558" />


**Question 6**
---
<img width="862" height="577" alt="image" src="https://github.com/user-attachments/assets/8064486b-967d-4b6a-8620-cbfe70c11a31" />

```sql
select *
from CUSTOMERS
where AGE <30;
```

**Output:**

<img width="1265" height="802" alt="image" src="https://github.com/user-attachments/assets/f0b32ec5-a781-4f09-9fd5-f7cfb83d93af" />


**Question 7**
---
<img width="1057" height="362" alt="image" src="https://github.com/user-attachments/assets/a613dcd8-1f9c-4f8f-81ec-16f1e2073f33" />


```sql
select grade, COUNT(*)
from customer
group by grade
having grade > (select AVG(grade) from customer where city='New York' );
```

**Output:**

<img width="1290" height="735" alt="image" src="https://github.com/user-attachments/assets/532a696f-06f9-4cc2-a25e-6d864ac9eed2" />


**Question 8**
---
<img width="1132" height="562" alt="image" src="https://github.com/user-attachments/assets/b6b9edb4-1f51-48e9-8d87-dffec09906ad" />


```sql
select *
from ORDERS
where salesman_id in (select salesman_id from SALESMAN where city='New York');
```

**Output:**

<img width="1260" height="790" alt="image" src="https://github.com/user-attachments/assets/6d69882a-3fba-43b0-bfd6-dcefa84d766b" />


**Question 9**
---
<img width="838" height="402" alt="image" src="https://github.com/user-attachments/assets/26bc0947-63b0-4b1b-a100-3d7e998bcbb4" />


```sql
select *
from customer
where city  != (select city from customer where id = (select MAX(id) from customer));
```

**Output:**

<img width="1290" height="776" alt="image" src="https://github.com/user-attachments/assets/f3f22fe0-57d8-4fe3-8f73-a1eba4ac9c0c" />


**Question 10**
---
<img width="881" height="538" alt="image" src="https://github.com/user-attachments/assets/78c54ca6-359a-4998-a56d-21b6811aec1c" />


```sql
select *
from customer
where customer_id = (select salesman_id -2001 from salesman where name='Mc Lyon');
```

**Output:**

<img width="1278" height="695" alt="image" src="https://github.com/user-attachments/assets/0b9651ce-99fe-40c2-b4fd-6fb09fa21d85" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
