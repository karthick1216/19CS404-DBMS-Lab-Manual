# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="1272" height="637" alt="image" src="https://github.com/user-attachments/assets/a57f53ec-f3da-4862-84df-94ccc8508991" />


```sql
select s.name ,c.cust_name,c.city,c.grade,s.salesman_id
from salesman s
left join customer c
on s.salesman_id=c.salesman_id;
```

**Output:**

<img width="1283" height="747" alt="image" src="https://github.com/user-attachments/assets/514657e1-ce7e-400d-ac4d-f4b193910cbe" />

**Question 2**
---
<img width="1287" height="470" alt="image" src="https://github.com/user-attachments/assets/554a3dad-73b5-43fa-9659-74f4223700fd" />


```sql
select p.*
from patients p
inner join test_results t
on t.patient_id=p.patient_id
where (t.test_name = 'Blood Test'or t.test_name='Blood Pressure') and t.result Not LIKE '%Normal%';
```

**Output:**

<img width="1257" height="742" alt="image" src="https://github.com/user-attachments/assets/47d55097-0c18-446d-a886-0613a214dc8d" />

**Question 3**
---
<img width="1283" height="503" alt="image" src="https://github.com/user-attachments/assets/c0d84a6e-e7a7-40e7-969c-761d71abf978" />


```sql
select c.cust_name
from ORDERS o
left join customer c
on o.customer_id=c.customer_id
where o.purch_amt <100;
```

**Output:**

<img width="1287" height="801" alt="image" src="https://github.com/user-attachments/assets/0b3affc3-ff8a-4658-8659-326c13f3fb09" />

**Question 4**
---
<img width="1295" height="485" alt="image" src="https://github.com/user-attachments/assets/c0756f6d-d746-4ef0-add7-3d30aac8e169" />


```sql
select p.first_name as patient_name , t.*
from test_results t
inner join patients p
on t.patient_id=p.patient_id
where t.test_name='Blood Pressure';

```

**Output:**

<img width="1301" height="751" alt="image" src="https://github.com/user-attachments/assets/8d6338b1-e976-43f3-941b-baeb81d2b27e" />


**Question 5**
---
<img width="1282" height="482" alt="image" src="https://github.com/user-attachments/assets/2485aca0-9bb5-4b8e-85ba-327a6838f1c0" />


```sql
select c.*
from customer c
left join ORDERS o
on c.customer_id=o.customer_id
where o.ord_date between '2012-08-01' and '2012-08-30';
```

**Output:**

<img width="1283" height="785" alt="image" src="https://github.com/user-attachments/assets/e50a1a2f-0386-45f8-9d89-82b00a29cbd6" />


**Question 6**
---
<img width="1101" height="750" alt="image" src="https://github.com/user-attachments/assets/6db80168-41a3-4822-90aa-9b1336d63a01" />


```sql
select  o.ord_no,o.ord_date,o.purch_amt,c.cust_name as 'Customer Name',c.grade,s.name as "Salesman", s.commission
from orders o
inner join customer c on o.customer_id=c.customer_id
inner join salesman s on o.salesman_id=s.salesman_id;
```

**Output:**

<img width="1345" height="642" alt="image" src="https://github.com/user-attachments/assets/d4543040-219d-4f5c-b96b-f164e53eba14" />


**Question 7**
---
<img width="1167" height="412" alt="image" src="https://github.com/user-attachments/assets/7664b550-6bb0-493d-b21f-70c5b18d6b72" />


```sql
select s.name as salesman_name,c.cust_name as customer_name
from salesman s
left join customer c
on c.salesman_id=s.salesman_id

```

**Output:**

<img width="1343" height="767" alt="image" src="https://github.com/user-attachments/assets/5ab3febe-c579-4429-9646-b30e87c10be0" />

**Question 8**
---
<img width="836" height="486" alt="image" src="https://github.com/user-attachments/assets/85cd4321-d25f-498a-80d0-f5b5af6708e7" />

```sql
select DISTINCT c.cust_name as "Customer Name",c.city,s.name as 'Salesman',s.commission
from customer c
inner join  salesman s
on c.salesman_id=s.salesman_id;
```

**Output:**

<img width="1343" height="697" alt="image" src="https://github.com/user-attachments/assets/f4ef80ac-d1d0-4245-b6ad-ed7605c9e1a6" />


**Question 9**
---
<img width="1042" height="325" alt="image" src="https://github.com/user-attachments/assets/21742a0b-5918-40f4-bf21-630b1e9e3c0e" />


```sql
select s.name
from salesman s
left join customer c
on s.salesman_id=c.salesman_id
where c.city='London';
```

**Output:**

<img width="1370" height="591" alt="image" src="https://github.com/user-attachments/assets/441baa9f-de4a-411d-a745-aa5f6eace304" />


**Question 10**
---
<img width="777" height="498" alt="image" src="https://github.com/user-attachments/assets/26a2b246-2dcb-40dc-9d00-41ce1fe47f62" />


```sql
select c.cust_name,c.city,c.grade,s.name as "Salesman",s.city
from salesman s
inner join customer c
on c.salesman_id=s.salesman_id
order by c.customer_id asc;
```

**Output:**

<img width="1335" height="687" alt="image" src="https://github.com/user-attachments/assets/40eea0c5-94bb-4332-83e4-a100b1587fba" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
