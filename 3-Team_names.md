
## Goal: List all the teams names for a single competition.

Create a list with all the team names for a single competition. Here, the competition will be the first competition with a name that begins with the letter 'A'. The team names in this competition will be listed in alphabetical order.

Tables used: Competitions, Teams

---
SQL code:

```
SELECT C.CompetitionName, T.TeamName
    FROM Competitions AS C
        JOIN Teams AS T ON C.Id = T.CompetitionId
WHERE CompetitionName = (SELECT CompetitionName FROM Competitions WHERE CompetitionName LIKE 'A%' Limit 1)
ORDER BY T.TeamName
;
```
---

##### Notes:

```
SELECT C.CompetitionName, T.TeamName
    FROM Competitions AS C
        JOIN Teams AS T ON C.Id = T.CompetitionId
```

* The above code will display the **CompetitionName** column from the **Competitions** table and will display the **TeamName** column from the **Teams** table.
* The alias **C** is used for the table **Competitions** and the alias **T** is used for the table **Teams**.
* The **Competitions** table will be joined with the **Teams** table by matching **ID** in **Competitions** with **CompetitionID** in **Teams**.

```
WHERE CompetitionName = (SELECT CompetitionName FROM Competitions WHERE CompetitionName LIKE 'A%' Limit 1)
```
* The above code is a conditions statement. The code will select only one competition, and the name of the competition must begin with the letter 'A'. 

```
ORDER BY T.TeamName
```
* The above code will list the team names in alphabetical order. 

[See results here!](https://www.kaggle.com/lochleven/meta-kaggle/competition-list1/run/97745/files) 
