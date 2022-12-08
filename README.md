
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

```MySQL
# Please write a DELETE statement and DO NOT write a SELECT statement.
DELETE p1
FROM Person AS p1, Person AS p2
WHERE p1.email = p2.email
AND p1.id > p2.id;
```







