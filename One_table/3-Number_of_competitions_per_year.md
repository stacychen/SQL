
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
---
Notes:


* The above code will extract year from the **dateEnabled** column from the **Competitions** table. The column displaying the years will be renamed as **Year**.  
* The above code will also count the total number of competitions for the given years. The column will be renamed as **Number of Competitions**.  
* The GROUP BY statement will group all the identical years together. 

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
---

* The above code will extract month from the **dateEnabled** column from the **Competitions** table. The column displaying the months will be renamed as **Month**.  
* The above code will also count the total number of competitions for the given months. The column will be renamed as **Number of Competitions**.  
* The WHERE statement will only select the months starting 2014-01-01 and before (but not including) 2015-01-01.
* The GROUP BY statement will group all the identical years together. 


Run this code [here](https://www.kaggle.com/lochleven/d/kaggle/meta-kaggle/competition-list1/edit)



