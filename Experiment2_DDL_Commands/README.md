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

Create a new table named item with the following specifications and constraints:


1.item_id as TEXT and as primary key.

2.item_desc as TEXT.

3.rate as INTEGER.

4.icom_id as TEXT with a length of 4.

5.icom_id is a foreign key referencing com_id in the company table.

6.The foreign key should cascade updates and deletes.

7.item_desc and rate should not accept NULL.

```

CREATE TABLE item(
item_id TEXT,
item_desc TEXT,
rate INT,
icom_id TEXT CHECK (LENGTH(icom_id)=4),
FOREIGN KEY (icom_id) REFERENCES company (com_id) ON UPDATE CASCADE ON DELETE CASCADE
);


```

**Output:**

![image](https://github.com/user-attachments/assets/644d225a-a9cc-4598-81d0-d50e409de9cd)


**Question 2**

Insert all books from Out_of_print_books into Books Table attributes are ISBN, Title, Author, Publisher, YearPublished

```

INSERT INTO Books (ISBN, Title, Author, Publisher, YearPublished)
SELECT ISBN, Title, Author, Publisher, YearPublished FROM Out_of_print_books;


```

**Output:**

![image](https://github.com/user-attachments/assets/6786250f-e4e4-48d8-a00b-fb209dd4f4f7)


**Question 3**


Write a SQL query to Add a new column Country as text in the Student_details table. Sample table: Student_details

```

ALTER TABLE Student_details ADD Country TEXT;

```

**Output:**

![image](https://github.com/user-attachments/assets/6e99facc-bfac-4f3d-9985-26045d187af8)


**Question 4**
Create a table named Locations with the following columns:

* LocationID as INTEGER
* LocationName as TEXT
* Address as TEXT

```

CREATE TABLE Locations(
LocationID INTEGER,
LocationName TEXT,
Address TEXT
);

```


**Output:**


![image](https://github.com/user-attachments/assets/88ad034f-6908-4858-9193-6fb73f892f6e)


**Question 5**


Insert a book with ISBN 978-1234567890, Title Data Science Essentials, Author Jane Doe, Publisher TechBooks, and Year 2024 into the Books table.


```

INSERT INTO Books (ISBN,Title,Author,Publisher,Year)
VALUES ('978-1234567890','Data Science Essentials','Jane Doe','TechBooks',2024);


```

**Output:**

![image](https://github.com/user-attachments/assets/f65cb5df-b9c3-4f44-843e-91dd9f3ef6c9)


**Question 6**


In the Student_details table, insert a student record where some fields are NULL, another record where all fields are filled without any NULL values, and a third record where some fields are filled, and others are left as NULL.

```

INSERT INTO Student_details (RollNo,Name,Gender,Subject,MARKS)
VALUES (205,'Olivia Green','F',NULL,NULL),
(207,'Liam Smith','M','Mathematics',85),
(208,'Sophia Johnson','F','Science',NULL);

```

**Output:**


![image](https://github.com/user-attachments/assets/cefe308d-4613-46aa-9895-f0273310f2a1)


**Question 7**

Create a table named Bonuses with the following constraints:

* BonusID as INTEGER should be the primary key.
* EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
* BonusAmount as REAL should be greater than 0.
* BonusDate as DATE.
* Reason as TEXT should not be NULL.

```

CREATE TABLE Bonuses(
BonusID INT PRIMARY KEY,
EmployeeID INT,
BonusAmount REAL,
BonusDate DATE,
Reason TEXT NOT NULL,
FOREIGN KEY (EmployeeID) REFERENCES Employees (EmployeeID),
CHECK (BonusAmount>0)
);

```

**OUTPUT:**


![image](https://github.com/user-attachments/assets/ad1dca9d-081e-414e-b091-1d454483688c)



**Question 8**

create a table named jobs including columns job_id, job_title, min_salary and max_salary, and make sure that, the default value for job_title is blank and min_salary is 8000 and max_salary is NULL will be entered automatically at the time of insertion if no value assigned for the specified columns.


```


CREATE TABLE jobs(
job_id INTEGER,
job_title TEXT DEFAULT 'black',
min_salary INT DEFAULT 8000,
max_salary INT DEFAULT NULL
);


```

**Output:**

![image](https://github.com/user-attachments/assets/b0a9c707-c2ce-4d86-a5c1-89cbfd33624b)



**Question 9**


Write an SQL Query to add the attributes designation, net_salary, and dob to the Companies table with the following data types:

* designation as VARCHAR(50)
* net_salary as NUMBER
* dob as DATE

```

ALTER TABLE Companies ADD designation varchar(50);
ALTER TABLE Companies ADD net_salary number;
ALTER TABLE Companies ADD dob date;

```

**Output:**

![image](https://github.com/user-attachments/assets/633734f5-12d2-48ae-9dfc-d8a2631b8272)


**Question 10**


Create a table named Invoices with the following constraints:

* InvoiceID as INTEGER should be the primary key.
* InvoiceDate as DATE.
* Amount as REAL should be greater than 0.
* DueDate as DATE should be greater than the InvoiceDate.
* OrderID as INTEGER should be a foreign key referencing Orders(OrderID).

```
CREATE TABLE Invoices(
InvoiceID INTEGER PRIMARY KEY,
InvoiceDate DATE,
Amount REAL,
DueDate DATE,
OrderID INTEGER,
FOREIGN KEY (OrderID) REFERENCES Orders (OrderID),
CHECK (LENGTH(Amount)>0),
CHECK (DueDate>InvoiceDate)
);

```

**Output:**

![image](https://github.com/user-attachments/assets/c159524e-e528-4c9a-b41a-c75f98670d82)



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
