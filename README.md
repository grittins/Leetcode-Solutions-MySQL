
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


