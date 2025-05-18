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

![image](https://github.com/user-attachments/assets/9b775844-e962-49cc-96fc-22d8138a7463)

```

SELECT 
    customer.cust_name AS "Customer Name", 
    customer.city AS "city", 
    salesman.name AS "Salesman", 
    salesman.commission
FROM 
    customer
JOIN 
    salesman
ON 
    customer.salesman_id = salesman.salesman_id
WHERE 
    salesman.commission > 0.12;

```


**Output:**

![image](https://github.com/user-attachments/assets/19b9089e-2ac8-47ca-a048-4d9e1c1403d3)



**Question 2**

![image](https://github.com/user-attachments/assets/d9f004e6-7bb6-47f8-be3c-0232675b9a5e)


```

SELECT 
    patients.date_of_birth, 
    appointments.*
FROM 
    patients
JOIN 
    appointments
ON 
    patients.patient_id = appointments.patient_id
WHERE 
    patients.first_name = 'Alice';



```

**Output:**

![image](https://github.com/user-attachments/assets/25119679-884c-467d-8102-e7c116e37967)


**Question 3**

![image](https://github.com/user-attachments/assets/3b291011-cfc3-4ac4-9081-a354021c9309)

```

SELECT 
    orders.ord_no, 
    orders.ord_date, 
    orders.purch_amt, 
    customer.cust_name AS "Customer Name", 
    customer.grade, 
    salesman.name AS "Salesman", 
    salesman.commission
FROM 
    orders
JOIN 
    customer ON orders.customer_id = customer.customer_id
JOIN 
    salesman ON orders.salesman_id = salesman.salesman_id;



```

**Output:**

![image](https://github.com/user-attachments/assets/f6e2ea5b-85c7-45e0-814d-a18eceb441ed)



**Question 4**


![image](https://github.com/user-attachments/assets/214d103f-0c12-4aaf-a2d2-ccc8fd110f8e)



```

SELECT 
    customer.cust_name, 
    customer.city, 
    customer.grade, 
    salesman.name AS "Salesman", 
    salesman.city AS "city"
FROM 
    customer
JOIN 
    salesman ON customer.salesman_id = salesman.salesman_id
WHERE 
    customer.grade < 300
ORDER BY 
    customer.customer_id ASC;



```

**Output:**


![image](https://github.com/user-attachments/assets/6dccb05f-b759-45fa-916b-a828293cc2bf)





**Question 5**

![image](https://github.com/user-attachments/assets/87d8fe44-2d80-4a0b-9b4b-39760c7ad410)


```

SELECT 
    s.name
FROM 
    salesman AS s
LEFT JOIN 
    customer AS c ON s.salesman_id = c.salesman_id
WHERE 
    c.city = 'London';


```
**Output:**

![image](https://github.com/user-attachments/assets/908c3176-36ce-4d42-a5ac-f620cfc374ff)



**Question 6**


![image](https://github.com/user-attachments/assets/5cd3ee53-3880-488c-a242-419481239f27)


```


SELECT 
    c.cust_name
FROM 
    customer AS c
LEFT JOIN 
    orders AS o ON c.customer_id = o.customer_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/85c49212-22e3-48ff-82e7-81335a711c68)


**Question 7**

![image](https://github.com/user-attachments/assets/3479d610-108b-45ba-a008-c4d6b31c2382)

```
SELECT 
    p.first_name AS patient_name, 
    t.*
FROM 
    patients AS p
INNER JOIN 
    test_results AS t ON p.patient_id = t.patient_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/2a2bf4cd-13af-45b2-a0fb-26faf72c7a9e)


**Question 8**

![image](https://github.com/user-attachments/assets/2cc94ee4-e2e0-46df-9ee4-ed88dcb962d5)

```

SELECT 
    c.cust_name, 
    c.city AS city, 
    c.grade, 
    s.name AS Salesman, 
    s.city AS city
FROM 
    customer c
LEFT JOIN 
    salesman s 
ON 
    c.salesman_id = s.salesman_id
ORDER BY 
    c.customer_id ASC;

```

**Output:**

![image](https://github.com/user-attachments/assets/10229fbe-32f9-4378-91c9-3ba2b65f098f)


**Question 9**


![image](https://github.com/user-attachments/assets/65ee3b2b-f033-4836-b5fa-666c03b178b7)


````

SELECT 
    p.admission_date, 
    s.surgery_date
FROM 
    patients p
INNER JOIN 
    surgeries s 
ON 
    p.patient_id = s.patient_id;

````

**Output:**

![image](https://github.com/user-attachments/assets/d911619f-d602-4cfd-82be-a4930f0130e7)


**Question 10**

![image](https://github.com/user-attachments/assets/2874c102-45b0-44e8-a124-08244c3acb0f)


```
SELECT 
    c.cust_name AS "Customer Name", 
    c.city, 
    s.name AS "Salesman", 
    s.commission
FROM 
    customer c
JOIN 
    salesman s 
ON 
    c.salesman_id = s.salesman_id;


```

**Output:**

![image](https://github.com/user-attachments/assets/a9a8008a-bfad-4083-a031-8ad332be062d)



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
