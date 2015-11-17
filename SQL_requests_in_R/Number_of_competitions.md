
### Goal: Create a bar graph displaying the number of competitions released each year.

---
SQL code:

```
library(readr)
library(RSQLite)

db <- dbConnect(dbDriver("SQLite"), "../input/database.sqlite")

request <- "
SELECT 
    strftime('%Y', dateEnabled) AS 'Year', 
    COUNT(*) AS 'Competitions'
FROM competitions
GROUP BY Year
"
comp_count <- dbGetQuery(db, request)

barplot(comp_count$Competitions, main = "Number of Competitions Per Year",
        names = comp_count$Year,
        xlab = 'Year', ylab = 'Frequency', col = 'blue2')
box()


```

---
[See results here!](https://www.kaggle.com/lochleven/meta-kaggle/competition-list1/run/105801)

### Create a bar graph showing the number of competitions released per month in the year 2014. 

---
SQL Code:
```
library(readr)
library(RSQLite)

db <- dbConnect(dbDriver("SQLite"), "../input/database.sqlite")

request <- "
SELECT 
    strftime('%m', dateEnabled) AS 'Month',
    COUNT('Month') AS 'Competitions'
FROM competitions
WHERE dateEnabled BETWEEN '2014-01-01' AND '2015-01-01'
GROUP BY Month
"
monthly_count <- dbGetQuery(db, request)

barplot(monthly_count$Competitions, main = "Number of Competitions Per Month in 2014",
        names = monthly_count$Month,
        xlab = 'Month', ylab = 'Frequency', col = 'green3',
        ylim = c(0,10))
box()

```
[See results here!](https://www.kaggle.com/lochleven/meta-kaggle/competition-list1/run/105935)

