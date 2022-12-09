
# Leetcode SQL l Study Plan Solutions solved using MySQL (https://leetcode.com/study-plan/sql)

## DAY 1

### 595 Big Countries
```MySQL
SELECT name, population, area
FROM World
WHERE area >= 3000000 OR population >= 25000000;
```
### 1757 Recyclable and Low Fat Products
```MySQL
SELECT product_id
FROM Products
WHERE low_fats = 'Y' AND recyclable = 'Y'
```
### 584 Find Customer Referee
```MySQL
SELECT name
FROM Customer
WHERE referee_id <> 2 OR referee_id IS NULL;
```
### 183 Customers Who Never Order
```MySQL
SELECT c.name AS Customers
FROM Customers AS c
LEFT JOIN Orders AS o
ON c.id = o.customerID
WHERE o.id IS NULL
ORDER BY c.name;
```

## DAY 2

### 1873 Calculate Special Bonus
```MySQL
SELECT employee_id, 
    (CASE 
    WHEN employee_id % 2 <> 0 AND name NOT LIKE 'M%'
    THEN salary
    ELSE 0 
    END) AS bonus
FROM Employees
ORDER BY employee_id;
```
### 627 Swap Salary
```MySQL
# Note that you must write a single update statement, do not write any select statement for this problem.
UPDATE Salary
SET sex =  
    CASE sex
    WHEN 'm' THEN 'f'
    ELSE 'm'
    END;
```
### 196 Delete Duplicate Emails
```MySQL
# Please write a DELETE statement and DO NOT write a SELECT statement.
DELETE p1
FROM Person AS p1, Person AS p2
WHERE p1.email = p2.email AND p1.id > p2.id;
```
## DAY 3

### 1667 Fix Names in a Table
```MySQL
SELECT user_id, CONCAT(UPPER(SUBSTR(name,1,1)), LOWER(SUBSTR(name,2))) AS name
FROM Users
ORDER BY user_id;

# CONCAT(A,B) where we concat two strings A+B

# UPPER(A) where A is string
# LOWER(A) where A is string
# SUBSTR(A,index,length) 
# where A is string index is starting index(indexing starts at 1) 
# and length (optional, if blank goes till end)

# To get first letter we can use SUBSTR(name,1,1)
# To get the remaining string we can use SUBSTR(name,2) - length is not required here
```
### 1484 Group Sold Products By The Date
```MySQL
SELECT sell_date, 
    COUNT(DISTINCT product) AS num_sold,  
    GROUP_CONCAT(DISTINCT product) AS products
FROM Activities
GROUP BY sell_date
ORDER BY sell_date;
```
### 1527 Patients With a Condition
```MySQL
SELECT patient_id, patient_name, conditions
FROM Patients
WHERE conditions LIKE '% DIAB1%' OR conditions LIKE 'DIAB1%';
```


