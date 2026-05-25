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

<img width="785" height="341" alt="3 1" src="https://github.com/user-attachments/assets/bac98de3-6a1d-4b79-907a-2f539e736138" />


```sql
delete from customer where GRADE=2;
```

**Output:**



<img width="767" height="599" alt="3 1a" src="https://github.com/user-attachments/assets/693fb4a8-09f3-450b-a2e1-539653209a5c" />


**Question 2**
---


<img width="496" height="297" alt="3 2" src="https://github.com/user-attachments/assets/08b7d40b-d60f-42a7-8761-b491a0fb55f2" />

```sql
select id, value1, case when value1>50 then 'High' else 'Low' end as value_category from Calculations;
```

**Output:**


<img width="448" height="132" alt="3 2a" src="https://github.com/user-attachments/assets/502b7f83-24a5-4c4b-a3ba-bff18106ec89" />

**Question 3**
---


<img width="456" height="281" alt="3 3" src="https://github.com/user-attachments/assets/3f38a1dc-c08e-4be4-a8b5-8b4c36dcc711" />

```sql
delete from Surgeries where surgery_date='2024-02-28';
```

**Output:**



<img width="644" height="177" alt="3 3a" src="https://github.com/user-attachments/assets/cece6b63-04ba-45c6-b6ab-99e1fdbf4887" />


**Question 4**
---


<img width="695" height="322" alt="3 4" src="https://github.com/user-attachments/assets/9fc7bcb2-cd3f-4302-832d-2ed5fa7843fc" />

```sql
select product_id, original_price, discount_percentage, ((1-discount_percentage)*original_price) as discounted_price from Products  order by original_price desc limit 2;
```

**Output:**


<img width="681" height="114" alt="3 4a" src="https://github.com/user-attachments/assets/7dfb70fc-8c8e-4ee0-af49-903fa35ff5d1" />


**Question 5**
---


<img width="464" height="269" alt="3 5" src="https://github.com/user-attachments/assets/52b6d7e4-540a-4678-8e07-95d973e4e2e3" />


```sql
select substr(EmpLname,1,4) as 'SUBSTR(EmpLname, 1, 4)' from EmployeeInfo;
```

**Output:**


<img width="338" height="157" alt="3 5a" src="https://github.com/user-attachments/assets/76413058-417b-4f43-a17a-b8c61c8a8157" />


**Question 6**
---

<img width="398" height="324" alt="3 6" src="https://github.com/user-attachments/assets/a4514792-ecd5-479c-b324-bf86367506bf" />


```sql
select ename, strftime('%d-%m-%Y',hiredate) as HireDateFormatted from emp;
```

**Output:**



<img width="353" height="181" alt="3 6a" src="https://github.com/user-attachments/assets/0da2962d-872e-4245-ad4e-c1474a842a81" />


**Question 7**
---

<img width="479" height="163" alt="3 7" src="https://github.com/user-attachments/assets/6aa4cf5e-e5dc-47ae-a962-8e3f11f5520e" />


```sql
update Products set quantity=quantity*1.10;
```

**Output:**


<img width="1097" height="298" alt="3 7a" src="https://github.com/user-attachments/assets/125f6993-0236-4e56-8745-78e0e145cbd1" />


**Question 8**
---

<img width="1223" height="441" alt="3 8" src="https://github.com/user-attachments/assets/3e668e86-408e-4361-9ee8-12846c41781b" />


```sql
update Products set reorder_lvl=20 where quantity<10 and category='Snacks';
```

**Output:**


<img width="1202" height="268" alt="3 8a" src="https://github.com/user-attachments/assets/32a07b07-0d7a-42ba-885c-0d3c5939db37" />

**Question 9**
---

<img width="636" height="323" alt="3 9" src="https://github.com/user-attachments/assets/eb537365-351e-4418-8920-4fe7de1a7278" />

```sql
update Employees set salary=salary*2 where department_id=20 and job_id like'%MAN';
```

**Output:**

<img width="927" height="166" alt="3 9a" src="https://github.com/user-attachments/assets/e9ac3da6-cd0d-4847-a10e-767f770d9742" />

**Question 10**
---
<img width="660" height="294" alt="3 10" src="https://github.com/user-attachments/assets/5986a4ce-2152-4bc7-b8e4-afd870c8f43a" />


```sql
select customer_id, cust_name, city, grade, salesman_id from customer where grade is NULL;
```

**Output:**

<img width="627" height="196" alt="3 10a" src="https://github.com/user-attachments/assets/24c8e8df-0489-4f70-8677-a6a8b092c302" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
