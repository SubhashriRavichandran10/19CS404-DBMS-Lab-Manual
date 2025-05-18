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

![image](https://github.com/user-attachments/assets/757f5454-9c95-4aaf-87b4-4e49df5d4c71)

```

SELECT * FROM CUSTOMERS WHERE AGE<30;

```
**Output:**

![image](https://github.com/user-attachments/assets/51fb6291-73b4-4840-a8aa-2c78862a707f)


**Question 2**

![image](https://github.com/user-attachments/assets/4996d3ab-9018-42b4-a0b8-0214c37bf0bb)

```

SELECT * FROM ORDERS WHERE salesman_id in (SELECT salesman_id FROM SALESMAN WHERE city='New York');


```
**Output:**

![image](https://github.com/user-attachments/assets/f2c36900-cce4-477b-b467-1bcd79b96110)


**Question 3**

![image](https://github.com/user-attachments/assets/4a143740-e261-4f56-a398-4d27caadaf74)

```

SELECT salesman_id, name FROM salesman WHERE salesman_id IN (SELECT salesman_id FROM customer GROUP BY salesman_id HAVING COUNT(customer_id)>1);


```

**Output:**

![image](https://github.com/user-attachments/assets/39b17c8d-0cc8-4eb3-9e5f-bf4efa129489)


**Question 4**

![image](https://github.com/user-attachments/assets/65cbb75f-b83e-42f7-9a89-f9ada720c1d6)

```


SELECT medication_id AS medic, medication_name, dosage FROM Medications WHERE dosage=(SELECT MAX(dosage) FROM Medications);

```

**Output:**

![image](https://github.com/user-attachments/assets/7366d821-fcb4-4272-9d75-c377349be237)


**Question 5**

![image](https://github.com/user-attachments/assets/f3fb64b0-d277-45d3-aae5-42db85a36755)

```

SELECT * FROM orders WHERE salesman_id IN (SELECT salesman_id FROM salesman WHERE city='London');

```
**Output:**

![image](https://github.com/user-attachments/assets/c21f7ac4-4615-425a-8748-ef8c6fd26751)


**Question 6**

![image](https://github.com/user-attachments/assets/01064941-0188-48d1-b100-2cdc7e95f163)

```

SELECT student_name, grade FROM GRADES WHERE (subject,grade) IN (SELECT subject,MIN(grade) FROM GRADES GROUP BY subject);


```

**Output:**

![image](https://github.com/user-attachments/assets/dc2054e1-ef31-4cd7-a7e0-c4cc9d06b75d)


**Question 7**

![image](https://github.com/user-attachments/assets/1d9fd182-af28-49f1-892b-c4aff0046a59)

```

SELECT * FROM orders WHERE purch_amt>(SELECT AVG(purch_amt) FROM orders WHERE ord_date='2012-10-10');


```
**Output:**

![image](https://github.com/user-attachments/assets/fceb76de-0414-46f6-bbcf-a0bd883569d9)


**Question 8**

![image](https://github.com/user-attachments/assets/813c0759-7bc9-45ac-96f4-96e28aa43035)

```

SELECT * FROM GRADES WHERE (grade,subject) IN (SELECT MAX(grade),subject FROM GRADES GROUP BY subject);

```

**Output:**

![image](https://github.com/user-attachments/assets/4391bd56-768c-47f5-9958-3b7068256f83)


**Question 9**

![image](https://github.com/user-attachments/assets/15d26019-7ab2-46f7-984e-703837a1b20f)

```

SELECT * FROM CUSTOMERS WHERE salary=1500;

```

**Output:**

![image](https://github.com/user-attachments/assets/138514d0-9399-4604-92dc-a9f164b8d1ef)


**Question 10**

![image](https://github.com/user-attachments/assets/1d34c1dc-adab-4f60-8d38-3e25590d9b82)

```

SELECT * FROM employee WHERE age < (SELECT AVG(age) FROM employee WHERE income > 250000);


```
**Output:**

![image](https://github.com/user-attachments/assets/e2174e40-daa0-4765-b72b-a459731e965f)


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
