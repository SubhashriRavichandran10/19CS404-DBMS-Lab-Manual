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

![image](https://github.com/user-attachments/assets/7648f9d0-cbf8-4e38-9f16-4731aa4bb30d)


```
UPDATE suppliers SET supplier_name='A1 Suppliers' WHERE supplier_id=8;

```

**Output:**

![image](https://github.com/user-attachments/assets/c02763ea-5fa2-41ef-ac7b-d3bb173b5de9)


**Question 2**



![image](https://github.com/user-attachments/assets/88c04280-458f-4938-a8b8-4b1054eaa805)


```

UPDATE customer SET grade=5 WHERE city='Chennai';

```


**Output:**

![image](https://github.com/user-attachments/assets/94da9d51-d849-45b6-bce2-30e60dcab19e)


**Question 3**


![image](https://github.com/user-attachments/assets/4d6b2a11-d307-4ed8-b02e-097401fa1499)



```

UPDATE Employees SET salary=round(salary*1.25,1) WHERE department_id=40;
UPDATE Employees SET salary=round(salary*1.15,1) WHERE department_id=90;
UPDATE Employees SET salary=round(salary*1.1,1) WHERE department_id=110;

```


**Output:**


![image](https://github.com/user-attachments/assets/c884b319-386c-4368-8f6c-3a9b12437c7d)




**Question 4**


![image](https://github.com/user-attachments/assets/fd7a7a70-f7db-4224-b0ce-afd19be4b838)




```

UPDATE Suppliers SET address="58 Lakeview, Magnolia" WHERE supplier_id=5;

```

**Output:**



![image](https://github.com/user-attachments/assets/3e863d95-02ab-41a6-8907-b499f2946210)



**Question 5**



![image](https://github.com/user-attachments/assets/d0ed280c-df00-4c02-bd90-5cf566ff3a5e)


```

UPDATE products SET product_name='Premium Bread' WHERE product_id=5;


```


**Output:**

![image](https://github.com/user-attachments/assets/acc0665f-aaa8-4b4d-9623-e5cd21ad8f98)



**Question 6**


![image](https://github.com/user-attachments/assets/8a6e35d9-14cc-46bb-9aca-653defc85289)

```
DELETE FROM Doctors WHERE doctor_id BETWEEN 2 AND 4;


```


**Output:**


![image](https://github.com/user-attachments/assets/4cc52f8f-bfa3-4a8e-8408-e47432f8f2a1)


**Question 7**


![image](https://github.com/user-attachments/assets/fe7b4750-7f0a-4417-8772-f384326b4ef6)



```

DELETE FROM Doctors WHERE specialization IS NULL;


```

**Output:**


![image](https://github.com/user-attachments/assets/231ed0b4-bc72-4a9c-b93f-c31f4f36bde9)






**Question 8**


![image](https://github.com/user-attachments/assets/7a14d2af-0753-4543-b32d-1d119b609475)



```

DELETE FROM Doctors WHERE last_name IS NULL;

```

**Output:**

![image](https://github.com/user-attachments/assets/f2cc8462-ed86-467d-81c3-9074c2541645)


**Question 9**

![image](https://github.com/user-attachments/assets/713092e5-37cc-47b9-8d9b-d254d2bb3f75)



```

DELETE FROM Customer WHERE (GRADE=3 OR AGENT_CODE='A008') AND OUTSTANDING_AMT<5000;

```

**Output:**

![image](https://github.com/user-attachments/assets/59501127-663f-48bc-b381-200be2028d05)


**Question 10**


![image](https://github.com/user-attachments/assets/9d9bfaf9-1eec-4f99-9170-78845c965436)


```

DELETE FROM Customer WHERE GRADE<2;

```

**Output:**


![image](https://github.com/user-attachments/assets/f26829d9-d131-4f8a-9bd7-7c22a11f8f09)



## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
