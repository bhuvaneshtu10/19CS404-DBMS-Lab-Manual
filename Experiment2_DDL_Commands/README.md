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

<img width="686" height="286" alt="2 1" src="https://github.com/user-attachments/assets/65e7b6cf-7aff-49ad-8d25-f2a954fd043f" />

```sql
create table products(product_id integer primary key, product_name text not null, list_price decimal(10,2) not null, discount decimal(10,2) not null default 0, check(list_price>=discount), check(discount>=0), check(list_price>=0));
```

**Output:**

<img width="941" height="177" alt="2 1a" src="https://github.com/user-attachments/assets/6c8d80b8-5e90-4123-add9-68dd2a00c3ed" />


**Question 2**
---
<img width="981" height="431" alt="2 2" src="https://github.com/user-attachments/assets/2b8e0bb0-abfd-4548-ba76-c1e96dec883d" />


```sql
insert into Customers(CustomerID,Name,Address) values(304,'Peter Parker','Spider St');
```

**Output:**
<img width="1139" height="278" alt="2 2a" src="https://github.com/user-attachments/assets/7889ccd1-1efc-456b-a2a0-ad09a06cb20e" />


**Question 3**
---
<img width="1211" height="330" alt="2 3" src="https://github.com/user-attachments/assets/95f7701b-571c-4dbc-a94d-75bb21dd9033" />

```sql
create table Shipments(ShipmentID integer primary key, ShipmentDate date, SupplierID integer, OrderID integer, foreign key(SupplierID)references Suppliers, foreign key(OrderID)references Orders);
```

**Output:**
<img width="1293" height="151" alt="2 3a" src="https://github.com/user-attachments/assets/0f8e4c30-8c7e-4295-96bc-41e0c07b6f79" />


**Question 4**
---

<img width="803" height="434" alt="2 4" src="https://github.com/user-attachments/assets/54830719-df10-416e-851f-5787c3e4a535" />

```sql
alter table Student_details add column State TEXT;
```

**Output:**

<img width="1232" height="222" alt="2 4a" src="https://github.com/user-attachments/assets/0100e622-2273-4d34-95cd-ef32b92de83a" />


**Question 5**
---
<img width="942" height="447" alt="2 5" src="https://github.com/user-attachments/assets/4c9f2985-4be3-4558-8d9d-a8d104abbecb" />


```sql
alter table customer add column birth_date timestamp;
```

**Output:**
<img width="1771" height="241" alt="2 5a" src="https://github.com/user-attachments/assets/f794dcbe-4f70-4716-8f3b-a12de1b04e8e" />


**Question 6**
---

<img width="1274" height="438" alt="2 6" src="https://github.com/user-attachments/assets/0a3b78f2-6566-4c6d-9d7e-7505a26a32f2" />


```sql
create table Departments(DepartmentID INTEGER, DepartmentName TEXT);
```

**Output:**

<img width="1232" height="195" alt="2 6a" src="https://github.com/user-attachments/assets/c4c355f8-f261-4969-b181-74873b6fbcc7" />


**Question 7**
---
<img width="799" height="179" alt="2 7" src="https://github.com/user-attachments/assets/39208137-d7ab-439b-bf8e-72ccc4df415c" />


```sql
insert into student_details(RollNo,Name,Gender,Subject,MARKS) values(201,'David Lee','M','Physics',92);
```

**Output:**

<img width="1146" height="110" alt="2 7a" src="https://github.com/user-attachments/assets/e9103e3e-2ae3-47df-9882-e759be32b153" />

**Question 8**
---
<img width="920" height="191" alt="2 8" src="https://github.com/user-attachments/assets/9337bd98-c222-4f31-a70b-0be72c9bbf87" />


```sql
insert into Customers(CustomerID,Name,Address,City,Zipcode) values(301,'Michael Jordan','123 Maple St','Chicago',60616);
```

**Output:**

<img width="1217" height="116" alt="2 8a" src="https://github.com/user-attachments/assets/791470d5-37ab-4534-8741-7b45457e021b" />


**Question 9**
---

<img width="1454" height="304" alt="2 9" src="https://github.com/user-attachments/assets/06ba7142-d0f3-4b74-8ce8-bc446a458ea6" />


```sql
create table Bonuses(BonusID integer primary key,EmployeeID integer, BonusAmount real check(BonusAmount>0),BonusDate date, Reason text not null, foreign key(EmployeeID)references Employees(EmployeeID));
```

**Output:**

<img width="1632" height="129" alt="2 9a" src="https://github.com/user-attachments/assets/340d0fe5-a06f-4be1-8f94-ad3a340301bd" />


**Question 10**
---
<img width="1045" height="464" alt="2 10" src="https://github.com/user-attachments/assets/5702aa1e-58ef-4e3b-b747-313ba0fb0d2e" />


```sql
create table item(item_id text primary key, item_desc text, rate integer, icom_id text check(length(icom_id)=4), foreign key(icom_id)references company(com_id) on update set null on delete set null);
```

**Output:**

<img width="1330" height="238" alt="2 10a" src="https://github.com/user-attachments/assets/df4e94c3-ab5d-45e2-b52a-21fb0ee834e3" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
