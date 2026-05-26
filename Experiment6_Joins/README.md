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

<img width="1153" height="382" alt="6 1" src="https://github.com/user-attachments/assets/eeaee75a-93a1-4a2e-a6d7-943b8eb83aa4" />


```sql
select p.first_name,s.surgery_id,s.patient_id,s.surgeon_id, s.surgery_date from PATIENTS p inner join SURGERIES s on p.patient_id=s.patient_id where p.first_name='Alice';
```

**Output:**


<img width="801" height="175" alt="6 1a" src="https://github.com/user-attachments/assets/ac61bbcd-1820-4149-8a31-38ff3ecb7bf0" />


**Question 2**
---


<img width="967" height="217" alt="6 2" src="https://github.com/user-attachments/assets/d85eece0-f385-4922-a8ba-65ad41115507" />

```sql
select c.* from Customer as c left join salesman as s on c.salesman_id=s.salesman_id where s.name='Mc Lyon';
```

**Output:**


<img width="783" height="175" alt="6 2a" src="https://github.com/user-attachments/assets/c91c933b-bc6e-494b-b784-f1e500e2d3fd" />


**Question 3**
---

<img width="1297" height="196" alt="6 3" src="https://github.com/user-attachments/assets/013f635b-e842-4f4e-aedf-dde2ff5cac3c" />


```sql
select p.* from PATIENTS p inner join TEST_RESULTS t on p.patient_id=t.patient_id where (t.test_name='Blood Test' or t.test_name='Blood Pressure') and t.result not like '%Normal%';
```

**Output:**


<img width="1072" height="175" alt="6 3a" src="https://github.com/user-attachments/assets/2c747701-0410-4834-a4e3-863b35188cfd" />


**Question 4**
---

<img width="1378" height="381" alt="6 4" src="https://github.com/user-attachments/assets/d3a262b2-60a9-41c0-9bcd-914a8f3ab193" />


```sql
select p.first_name as patient_name, d.specialization as Doctor_specialization from PATIENTS p inner join DOCTORS d on p.doctor_id=d.doctor_id where admission_date between '2024-01-01' and '2024-01-31';
```

**Output:**


<img width="360" height="168" alt="6 4a" src="https://github.com/user-attachments/assets/d1c10775-b7b9-460a-9ec3-e11383f8ae33" />


**Question 5**
---

<img width="1023" height="363" alt="6 5" src="https://github.com/user-attachments/assets/a20d55f1-f0fb-432d-ac30-b7bef759e4e2" />


```sql
select c.cust_name,c.city,o.ord_no,o.ord_date,o.purch_amt as 'Order Amount' from customer c left join orders o on c.customer_id=o.customer_id order by o.ord_date asc;
```

**Output:**


<img width="804" height="578" alt="6 5a" src="https://github.com/user-attachments/assets/73411914-c3d7-4790-a26f-cd4a0181f8a5" />


**Question 6**
---

<img width="1022" height="202" alt="6 6" src="https://github.com/user-attachments/assets/f3fc3230-126d-41cd-892f-1f05506fc707" />


```sql
select n.* from NURSES n inner join DEPARTMENTS d on n.department_id=d.department_id where department_name='Pediatrics';
```

**Output:**


<img width="671" height="174" alt="6 6a" src="https://github.com/user-attachments/assets/8f3c105a-1e9c-4f92-8ea1-ee34b20ef257" />


**Question 7**
---


<img width="1077" height="370" alt="6 7" src="https://github.com/user-attachments/assets/397188ec-bdea-422f-94ec-a55725a7d2cd" />


```sql
select p.first_name,p.last_name from PATIENTS p inner join SURGERIES s on p.patient_id=s.patient_id where s.surgery_date between '2024-01-01' and '2024-01-31';
```

**Output:**


<img width="371" height="175" alt="6 7a" src="https://github.com/user-attachments/assets/dcdf43e4-76b2-4181-bbcf-febce2de88f2" />


**Question 8**
---

<img width="736" height="201" alt="6 8" src="https://github.com/user-attachments/assets/d4c8dd7f-0413-4fe3-a8fd-60822e01ef8f" />


```sql
select c.cust_name from CUSTOMER c left join ORDERS o on c.customer_id=o.customer_id ;
```

**Output:**


<img width="210" height="575" alt="6 8a" src="https://github.com/user-attachments/assets/adeda65b-19d1-4f39-bdcd-d7ed5b3c0f7a" />

**Question 9**
---


<img width="1151" height="367" alt="6 9" src="https://github.com/user-attachments/assets/9a23c6bd-f6b0-47da-8cea-14c7cf672b9e" />


```sql
select p.* from PATIENTS p inner join DOCTORS d on p.doctor_id=d.doctor_id where d.first_name='John' and d.last_name='Smith';
```

**Output:**


<img width="1067" height="173" alt="6 9a" src="https://github.com/user-attachments/assets/52164337-bd83-401c-a731-331835b62ce7" />


**Question 10**
---


<img width="1096" height="196" alt="6 10" src="https://github.com/user-attachments/assets/b51b1862-951f-40af-9724-dba899bc1e6d" />


```sql
select c.* from CUSTOMER c left join ORDERS o on c.salesman_id=o.salesman_id where o.ord_date between '2012-08-01' and '2012-08-30';
```

**Output:**


<img width="787" height="211" alt="6 10a" src="https://github.com/user-attachments/assets/6ec91749-d15d-445c-ae99-bd1d7a673281" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
