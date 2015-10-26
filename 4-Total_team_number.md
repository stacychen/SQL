

## Goal: Calculate the number of teams in a particular competition

```
SELECT C.CompetitionName, COUNT(T.TeamName)
  FROM Competitions C
JOIN Teams T ON C.Id = T.CompetitionId
  WHERE CompetitionName = (SELECT CompetitionName 
    FROM Competitions WHERE CompetitionName LIKE 'B%' Limit 1);

```
