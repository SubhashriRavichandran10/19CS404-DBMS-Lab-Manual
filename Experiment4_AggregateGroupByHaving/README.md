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

![image](https://github.com/user-attachments/assets/82b3c373-ca16-40de-9583-bc0dadc20865)


```

SELECT DoctorID, COUNT(RecordID) AS TotalRecords FROM MedicalRecords GROUP BY DoctorID;

```

**Output:**

![image](https://github.com/user-attachments/assets/ba70b2b6-613d-405e-8f33-84b85dc16a7d)


**Question 2**

![image](https://github.com/user-attachments/assets/32b83332-198f-45c0-aa49-690f113925b1)

```
SELECT InsuranceCompany, SUM(DATE('now')>SUBSTR(ValidityPeriod,15)) AS TotalExpiredPatients 
FROM Insurance GROUP BY InsuranceCompany;

```

**Output:**

![image](https://github.com/user-attachments/assets/b2d6b30d-8dca-473c-befe-b9a3764877bf)


**Question 3**

![image](https://github.com/user-attachments/assets/6e6ad517-dc17-42e5-88c6-eecc6995b406)


```

SELECT Frequency, COUNT(PrescriptionID) AS TotalPrescriptions FROM Prescriptions GROUP BY Frequency;

```

**Output:**

![image](https://github.com/user-attachments/assets/51aedc32-d3bf-4e4a-9ab3-8a13f3e4fec1)


**Question 4**

![image](https://github.com/user-attachments/assets/40a10f2b-4cec-447e-9324-e039829b0561)

```

SELECT sum(purch_amt) AS TOTAL FROM orders;

```

**Output:**

![image](https://github.com/user-attachments/assets/845be304-3f75-40f0-8948-19146e5066ef)


**Question 5**

![image](https://github.com/user-attachments/assets/e109f46d-d4a6-42f0-89db-afa6013e3adb)
`
```


SELECT COUNT(distinct salesman_id) AS COUNT FROM orders;

```

**Output:**

![image](https://github.com/user-attachments/assets/bf181f4a-c95b-4ec5-8239-eca9075f747e)


**Question 6**

![image](https://github.com/user-attachments/assets/833d7651-02d3-4502-a0eb-4b5c8230ae65)


```

SELECT COUNT(city) AS COUNT FROM customer GROUP BY city HAVING city='Noida'; 

```

**Output:**

![image](https://github.com/user-attachments/assets/9a939058-402c-48aa-8a66-8532dbcfbd3e)


**Question 7**

![image](https://github.com/user-attachments/assets/e21b44c1-15ae-4d31-ba0c-6544f9d9d071)

```

SELECT COUNT(distinct city) AS unique_cities FROM customer;

```

**Output:**



![image](https://github.com/user-attachments/assets/0e3f97e0-5f3d-49db-b15e-fcb9068316ad)



**Question 8**


![image](https://github.com/user-attachments/assets/9d0d91cf-e9b4-499a-8667-875851d22686)

```

SELECT (age/5)*5 AS age_group, sum(salary) AS 'SUM(salary)' FROM customer1 GROUP BY age_group HAVING sum(salary)>5000;

```

**Output:**


![image](https://github.com/user-attachments/assets/451e3c59-214e-4547-aa64-5cb8549d71be)


**Question 9**


![image](https://github.com/user-attachments/assets/1007510e-367c-45ef-afe4-2f4f665aa2b5)

```

SELECT occupation, min(workhour) AS 'MIN(workhour)' FROM employee1 GROUP BY occupation HAVING MIN(workhour)>=8;


```


**Output:**


![image](https://github.com/user-attachments/assets/695d4eba-21ad-4996-81b1-b267fa017c0f)


**Question 10**


![image](https://github.com/user-attachments/assets/a789cded-4e53-4c1a-ba5d-5f2697bcffb0)

```

SELECT category_id, COUNT(product_name) AS 'count(product_name)' FROM products GROUP BY category_id HAVING min(category_id)<3;

```

**Output:**


![image](https://github.com/user-attachments/assets/66291d40-90aa-47c8-a5ba-5c75978f5804)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
