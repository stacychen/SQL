
## Goal: Find the total number of competitions every year.

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




