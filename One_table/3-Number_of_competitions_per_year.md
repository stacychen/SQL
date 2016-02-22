
### Goal: Find the total number of competitions every year.

Table used: Competitions

---
SQL code:

```
SELECT 
    strftime('%Y', dateEnabled) AS 'Year', 
    COUNT(*) AS 'Number of Competitions'
FROM competitions
GROUP BY Year
```
Notes:





Run this code [here](https://www.kaggle.com/lochleven/d/kaggle/meta-kaggle/competition-list1/edit)

### Goal: Find the number of competitions per month for the year 2014.

---
SQL code:

```
SELECT 
    strftime('%m', dateEnabled) AS 'Month',
    COUNT('Month') AS 'Number of Competitions'
FROM competitions
WHERE dateEnabled BETWEEN '2014-01-01' AND '2015-01-01'
GROUP BY Month
```

Run this code [here](https://www.kaggle.com/lochleven/d/kaggle/meta-kaggle/competition-list1/edit)



