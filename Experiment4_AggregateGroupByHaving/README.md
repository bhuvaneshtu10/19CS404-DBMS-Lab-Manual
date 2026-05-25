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

<img width="442" height="243" alt="4 1" src="https://github.com/user-attachments/assets/7ebe4d56-e88f-431d-9790-8843cf92ac6d" />


```sql
select sum(income) as total_income from employee where age>=40;
```

**Output:**



<img width="179" height="132" alt="4 1a" src="https://github.com/user-attachments/assets/f929ca5c-84a3-439a-9246-da004853f3f8" />


**Question 2**
---


<img width="490" height="258" alt="4 2" src="https://github.com/user-attachments/assets/ec212037-17e8-466d-b7b2-d2433db2b453" />

```sql
select count(*) as COUNT from customer where grade is NOT NULL;
```

**Output:**


<img width="173" height="127" alt="4 2a" src="https://github.com/user-attachments/assets/921a1dbe-84e4-4bcc-91d1-f86e30642437" />


**Question 3**
---

<img width="397" height="234" alt="4 3" src="https://github.com/user-attachments/assets/3247e52e-363d-4a44-82b5-d74c84552b66" />


```sql
select avg(length(name)) as avg_name_length from customer where city='Chennai';
```

**Output:**



<img width="219" height="141" alt="4 3a" src="https://github.com/user-attachments/assets/17e880fa-acc0-4a8b-ab11-b35c80146019" />


**Question 4**
---

<img width="504" height="246" alt="4 4" src="https://github.com/user-attachments/assets/db810ec5-9c93-473a-8ffc-a81932f3ac27" />


```sql
select strftime('%Y-%m',Date) as Month, count(*) as TotalRecords from MedicalRecords group by strftime('%Y-%m',Date) order by Month;
```

**Output:**

<img width="302" height="187" alt="4 4a" src="https://github.com/user-attachments/assets/d71d32dc-7b54-4484-aae0-818b10cc6531" />


**Question 5**
---


<img width="502" height="275" alt="4 5" src="https://github.com/user-attachments/assets/4f060037-163c-4b15-a4cc-e0d7813df422" />

```sql
select Specialty,Gender, count(*) as TotalDoctors from Doctors group by Specialty, Gender order by Specialty, Gender;
```

**Output:**


<img width="462" height="297" alt="4 5a" src="https://github.com/user-attachments/assets/cd6227dd-d20d-45a8-92bd-93185e229a4d" />


**Question 6**
---


<img width="284" height="294" alt="4 6" src="https://github.com/user-attachments/assets/a05fd7e9-4dd4-4dda-ab89-149b3d3c90c6" />

```sql
select PatientID, count(*) as TotalAppointments from Appointments group by PatientID;
```

**Output:**


<img width="336" height="290" alt="4 6a" src="https://github.com/user-attachments/assets/8bafecdd-6388-46c7-b9af-6322ec3726dd" />


**Question 7**
---


<img width="843" height="258" alt="4 7" src="https://github.com/user-attachments/assets/72379b58-e7bd-49c9-af67-f4c9aaa9eb90" />

```sql
select city, AVG(income) from employee group by city having AVG(income)>500000;
```

**Output:**

<img width="284" height="189" alt="4 7a" src="https://github.com/user-attachments/assets/e699a97c-1b01-4801-b2ec-57faff57fb59" />



**Question 8**
---


<img width="879" height="225" alt="4 8" src="https://github.com/user-attachments/assets/2a03ef94-e9fe-4584-8f03-0a82398abe40" />


```sql
select category_id, AVG(price) as'AVG(Price)' from products group by category_id having price between 10 and 15;
```

**Output:**



<img width="279" height="138" alt="4 8a" src="https://github.com/user-attachments/assets/0b050387-cbf8-47d4-852e-fd8b7ac3445a" />


**Question 9**
---


<img width="925" height="243" alt="4 9" src="https://github.com/user-attachments/assets/7c75976d-b69d-4ab7-9bcd-2076c2d65c79" />


```sql
select jdate, min(workhour) as 'MIN(workhour)' from employee1 where workhour<10 group by jdate;
```

**Output:**


<img width="302" height="184" alt="4 9a" src="https://github.com/user-attachments/assets/2abc4bde-c5d0-4303-95ef-f7300786d56b" />


**Question 10**
---


<img width="920" height="235" alt="4 10" src="https://github.com/user-attachments/assets/d152b0c7-0ef1-472c-b1c7-96f2939cfc6e" />


```sql
select category_id, min(price) as 'Price' from products where price<10 group by category_id;
```

**Output:**



<img width="282" height="155" alt="4 10a" src="https://github.com/user-attachments/assets/9f4fbc16-4f7f-4e03-b2a4-4b52b82ca797" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
