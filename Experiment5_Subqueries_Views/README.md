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

<img width="487" height="256" alt="5 1" src="https://github.com/user-attachments/assets/573fbfeb-95ff-43b2-818c-9af2746e697a" />

```sql
select medication_id, medication_name, dosage from Medications where dosage=(select max(dosage) from Medications);
```

**Output:**


<img width="442" height="195" alt="5 1a" src="https://github.com/user-attachments/assets/c7b3823f-6ad7-4b59-b3aa-06e86f0a6bc9" />


**Question 2**
---

<img width="714" height="206" alt="5 2" src="https://github.com/user-attachments/assets/57793654-6af2-4036-bc52-98700ff7595e" />

```sql
select * from Orders where salesman_id in (select salesman_id from Salesman where city ='New York');
```

**Output:**



<img width="617" height="199" alt="5 2a" src="https://github.com/user-attachments/assets/dd777215-868e-4a16-8281-1e700e432971" />


**Question 3**
---


<img width="636" height="185" alt="5 3" src="https://github.com/user-attachments/assets/83636a94-8a1d-4c7d-a778-113a12502622" />


```sql
select * from GRADES g where grade=(select min(grade) from GRADES where subject=g.subject);
```

**Output:**





**Question 4**
---

<img width="591" height="359" alt="5 4" src="https://github.com/user-attachments/assets/634da0cf-dab1-4f9a-8f21-3de0fcf3d89a" />


```sql
select salesman_id, name from salesman where salesman_id in (select salesman_id from customer group by salesman_id having count(*)>1);
```

**Output:**


<img width="284" height="204" alt="5 4a" src="https://github.com/user-attachments/assets/384b9565-473d-4005-94ae-28bba5d47ba2" />


**Question 5**
---

<img width="478" height="329" alt="5 5" src="https://github.com/user-attachments/assets/4ae963fa-1cca-40db-be51-d6805b0dfe92" />


```sql
select * from CUSTOMERS where SALARY<2500;
```

**Output:**


<img width="600" height="208" alt="5 5a" src="https://github.com/user-attachments/assets/7351ec39-ef91-462c-a6b1-aed6b7e01165" />


**Question 6**
---


<img width="559" height="314" alt="5 6" src="https://github.com/user-attachments/assets/8fadc61f-d1e6-48af-95a8-19aa63eb9cf4" />


```sql
select * from Employee where age<(select avg(age) from Employee where income>1000000);
```

**Output:**


<img width="686" height="174" alt="5 6a" src="https://github.com/user-attachments/assets/fc157bba-da03-4c8a-b666-8a4929544598" />


**Question 7**
---


<img width="696" height="319" alt="5 7" src="https://github.com/user-attachments/assets/ba300711-1dba-44a9-a961-b7dac07ccdac" />


```sql
select student_name, grade from GRADES g where grade=(select min(grade) from GRADES where subject=g.subject);
```

**Output:**

<img width="367" height="188" alt="5 7a" src="https://github.com/user-attachments/assets/8c5b20cf-8b0a-40ed-a81e-33db8aeafd09" />


**Question 8**
---

<img width="451" height="255" alt="5 8" src="https://github.com/user-attachments/assets/e4964be9-577f-49ae-8027-3b92dd092bf4" />


```sql
select medication_id, medication_name, dosage from Medications where dosage=(select min(dosage) from Medications);
```

**Output:**


<img width="428" height="167" alt="5 8a" src="https://github.com/user-attachments/assets/fb3156b5-57fb-4c59-ab47-29f1fdbe2dea" />


**Question 9**
---

<img width="493" height="334" alt="5 9" src="https://github.com/user-attachments/assets/c03328b7-7797-4098-931b-5283d8367f25" />


```sql
select * from CUSTOMERS where SALARY>4500;
```

**Output:**

<img width="598" height="189" alt="5 9a" src="https://github.com/user-attachments/assets/a4288be9-a7f3-48ae-945d-12fa5fc99b7c" />


**Question 10**
---
<img width="534" height="271" alt="5 10" src="https://github.com/user-attachments/assets/da284cd6-fd2f-4ed6-9eb8-57f84b370b41" />


```sql
select name,city from customer where city in(select city from customer where id in(3,7));
```

**Output:**


<img width="273" height="204" alt="5 10a" src="https://github.com/user-attachments/assets/d9946e4d-1764-427c-830d-bd92877b9ab3" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
