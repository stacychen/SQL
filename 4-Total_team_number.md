

## Goal: Calculate the number of teams for one competition.

The goal is to calculate the number of teams for one selected competition. Here, the competition selected will be the first competition with a name that begins with the letter 'H'. 

```
SELECT C.CompetitionName, COUNT(T.TeamName)
  FROM Competitions C
JOIN Teams T ON C.Id = T.CompetitionId
  WHERE CompetitionName IN (SELECT CompetitionName FROM Competitions 
                            WHERE CompetitionName LIKE 'H%' 
                            ORDER BY CompetitionName LIMIT 1)
;
```
##### Notes:

```
SELECT C.CompetitionName, COUNT(T.TeamName)
  FROM Competitions C
```
* The above code will select the **CompetitionName** column from the **Competitions** table. The code will also count the number of teams that is associated for the selected competition. 

[See results here!](https://www.kaggle.com/lochleven/meta-kaggle/competition-list1/run/97821)
