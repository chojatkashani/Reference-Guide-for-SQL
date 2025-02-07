# Reference-Guide-for-SQL


---

## **Table of Contents**  
1. [Query a Database](#query-a-database)  
2. [Apply Filters to SQL Queries](#apply-filters-to-sql-queries)  
3. [Join Tables](#join-tables)  
4. [Perform Calculations](#perform-calculations)  

---

## **Query a Database**  

### **FROM** *(Specify Table to Query)*  
| Command | Description |
|---------|------------|
| `FROM employees` | Queries the **employees** table. |  

### **ORDER BY** *(Sort Query Results)*  
| Command | Description |
|---------|------------|
| `ORDER BY department` | Sorts results in **ascending order** by department. |
| `ORDER BY department ASC` | Same as above (explicit ascending order). |
| `ORDER BY city DESC` | Sorts results in **descending order** by city. |
| `ORDER BY country, city` | Sorts by **country**, then by **city**. |  

### **SELECT** *(Specify Columns to Retrieve)*  
| Command | Description |
|---------|------------|
| `SELECT employee_id` | Retrieves only the **employee_id** column. |
| `SELECT *` | Retrieves **all columns** from a table. |  

---

## **Apply Filters to SQL Queries**  

### **WHERE** *(Filter Query Results)*  
| Command | Description |
|---------|------------|
| `WHERE title = 'IT Staff'` | Filters results where **title** is **IT Staff**. |  

### **AND** *(Combine Conditions - Both Must Be Met)*  
| Command | Description |
|---------|------------|
| `WHERE region = 5 AND country = 'USA'` | Returns records where **region = 5** and **country = 'USA'**. |  

### **OR** *(Combine Conditions - Either Can Be Met)*  
| Command | Description |
|---------|------------|
| `WHERE country = 'Canada' OR country = 'USA'` | Returns records where **country** is **Canada** or **USA**. |  

### **BETWEEN** *(Filter Numeric or Date Ranges)*  
| Command | Description |
|---------|------------|
| `WHERE hiredate BETWEEN '2002-01-01' AND '2003-01-01'` | Returns records where **hiredate** is between **2002-01-01** and **2003-01-01**. |  

### **Comparison Operators** *(Filter Numeric or Date Values)*  
| Operator | Description | Example |
|----------|------------|---------|
| `=` | Equal to | `WHERE birthdate = '1980-05-15'` |
| `>` | Greater than | `WHERE birthdate > '1970-01-01'` |
| `>=` | Greater than or equal to | `WHERE birthdate >= '1965-06-30'` |
| `<` | Less than | `WHERE date < '2023-01-31'` |
| `<=` | Less than or equal to | `WHERE date <= '2020-12-31'` |  

### **LIKE** *(Search for Patterns in Text Columns)*  
| Command | Description |
|---------|------------|
| `WHERE title LIKE 'IT%'` | Matches **title** values starting with "IT". |
| `WHERE state LIKE 'N_'` | Matches **state** values starting with "N" followed by **one** character. |  

### **NOT** *(Negate a Condition)*  
| Command | Description |
|---------|------------|
| `WHERE NOT country = 'Mexico'` | Returns records where **country** is **not Mexico**. |  

### **NOT EQUAL TO Operators**  
| Operator | Description | Example |
|----------|------------|---------|
| `<>` | Not equal to | `WHERE date <> '2023-02-28'` |
| `!=` | Not equal to | `WHERE date != '2023-05-14'` |  

### **Wildcards for Pattern Matching**  
| Wildcard | Description | Example |
|----------|------------|---------|
| `%` | Matches **zero or more** characters | `'a%'` → Starts with 'a' |
| `_` | Matches **exactly one** character | `'a_'` → Starts with 'a', followed by one character |  

---

## **Join Tables**  

### **FULL OUTER JOIN** *(Return All Records from Both Tables)*  
```sql
SELECT * 
FROM employees 
FULL OUTER JOIN machines ON employees.device_id = machines.device_id;
```  

### **INNER JOIN** *(Return Only Matching Records Between Tables)*  
```sql
SELECT * 
FROM employees 
INNER JOIN machines ON employees.device_id = machines.device_id;
```  

### **LEFT JOIN** *(Return All Records from Left Table, Matching Only from Right Table)*  
```sql
SELECT * 
FROM employees 
LEFT JOIN machines ON employees.device_id = machines.device_id;
```  

### **RIGHT JOIN** *(Return All Records from Right Table, Matching Only from Left Table)*  
```sql
SELECT * 
FROM employees 
RIGHT JOIN machines ON employees.device_id = machines.device_id;
```  

---

## **Perform Calculations**  

### **AVG** *(Calculate Average of a Column)*  
```sql
SELECT AVG(height) FROM employees;
```  
Returns the **average height** from all records.  

### **COUNT** *(Count Number of Records in a Column)*  
```sql
SELECT COUNT(firstname) FROM employees;
```  
Returns the **total number of records** with a value in **firstname**.  

### **SUM** *(Calculate Sum of a Column)*  
```sql
SELECT SUM(cost) FROM purchases;
```  
Returns the **total cost** from all records.  

---

## **Summary**  

This **SQL reference guide** provides essential **commands** for:  
✅ **Querying databases**  
✅ **Filtering data**  
✅ **Joining tables**  
✅ **Performing calculations**  

Use this guide as a **quick reference** for executing **SQL queries** efficiently. 🚀  
