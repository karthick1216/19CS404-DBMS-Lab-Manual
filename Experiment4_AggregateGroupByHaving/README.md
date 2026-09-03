# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
<img width="1187" height="505" alt="image" src="https://github.com/user-attachments/assets/512f4ce3-c2cd-4126-9fb0-b88185635279" />


```sql
select count(grade) as "COUNT"
from customer;
```

**Output:**

<img width="1232" height="787" alt="image" src="https://github.com/user-attachments/assets/886016f7-94de-4b39-8cbb-d17af438c9a9" />

**Question 2**
---
<img width="1040" height="480" alt="image" src="https://github.com/user-attachments/assets/9cac7f35-48d1-4026-ac65-efe136365b96" />


```sql
select count(*) as "COUNT"
from employee
where age >32;
```

**Output:**

<img width="1292" height="741" alt="image" src="https://github.com/user-attachments/assets/2364784a-0738-449d-9378-bbbe4dd78fe8" />

**Question 3**
---
<img width="667" height="332" alt="image" src="https://github.com/user-attachments/assets/75e548f4-94b5-4923-b020-6f98642cc7d7" />


```sql
select count(*) as "employees_count"
from employee
where income>50000

```

**Output:**

<img width="1310" height="733" alt="image" src="https://github.com/user-attachments/assets/52b72b49-e1bc-4fcf-ba00-ff38f0454892" />


**Question 4**
---
<img width="938" height="422" alt="image" src="https://github.com/user-attachments/assets/323bc61e-ee76-41a5-aec7-a9c30c7fe451" />


```sql
select Frequency, count(*) as TotalPrescriptions
from Prescriptions
GROUP BY Frequency;
```

**Output:**

<img width="1306" height="757" alt="image" src="https://github.com/user-attachments/assets/be71edf8-a8a4-4d44-b081-fc0c208f4e0f" />


**Question 5**
---
<img width="698" height="495" alt="image" src="https://github.com/user-attachments/assets/9f642be1-f10d-42ee-ab77-a8af636c3c84" />


```sql
select InsuranceCompany, count(*) as TotalPatients
from Insurance
GROUP BY InsuranceCompany;
```

**Output:**

<img width="1282" height="800" alt="image" src="https://github.com/user-attachments/assets/a7093415-a2c3-43fe-9156-3cb54bc9cc5a" />


**Question 6**
---
<img width="582" height="421" alt="image" src="https://github.com/user-attachments/assets/f00a08d9-ab77-4bee-9bbb-bc111b92f2f9" />


```sql
select strftime('%Y',ValidityPeriod) as ValidityYear, count(*) as TotalPatients
from Insurance
group by strftime('%Y',validityPeriod)
order by ValidityYear ASC;
```

**Output:**

<img width="1271" height="770" alt="image" src="https://github.com/user-attachments/assets/36593a9a-1a4f-425b-9db7-cdb634d26484" />


**Question 7**
---
<img width="1283" height="387" alt="image" src="https://github.com/user-attachments/assets/ed320d27-cdba-49f6-9cb2-dde847e04ebb" />


```sql
select category_id , count(product_name) as "count(product_name)"
from products
GROUP BY category_id
HAVING min(category_id)<3
```

**Output:**

<img width="1293" height="727" alt="image" src="https://github.com/user-attachments/assets/94e01514-f9cd-4ba5-b8ac-6ff9a9bd4d09" />


**Question 8**
---
<img width="1242" height="401" alt="image" src="https://github.com/user-attachments/assets/4f9e5e43-f6aa-4876-9386-d860bc6ae17e" />

```sql
select age,SUM(income)
from employee
group by age
having SUM(income)>1000000;
```

**Output:**

<img width="1280" height="802" alt="image" src="https://github.com/user-attachments/assets/73bd374f-8138-4425-bd45-988c02680596" />

**Question 9**
---
<img width="1250" height="382" alt="image" src="https://github.com/user-attachments/assets/453f51c8-5933-45d5-8e5a-330dc943088b" />


```sql
select occupation , AVG(workhour)
from employee1
group by occupation
having avg(workhour) between 10 and 12;
```

**Output:**

<img width="1300" height="750" alt="image" src="https://github.com/user-attachments/assets/3ec7768f-5064-4b5d-b9b5-f19e931d64f6" />


**Question 10**
---
<img width="1291" height="376" alt="image" src="https://github.com/user-attachments/assets/4702c020-39ca-4bf8-953e-9d51398f44f2" />

```sql
select category_id ,SUM(price) as Total_Cost
from products
group by category_id
having SUM(price) >50;
```

**Output:**

<img width="1268" height="762" alt="image" src="https://github.com/user-attachments/assets/83ddcbf0-f30a-484b-9b1a-67d1650dbf10" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
