
## Goal: List all the teams (names) for one particular competition

Tables used: Competitions, Teams

```
SELECT C.CompetitionName, T.TeamName
    FROM Competitions AS C
JOIN Teams AS T ON C.Id = T.CompetitionId

WHERE CompetitionName = (SELECT DISTINCT CompetitionName 
    FROM Competitions WHERE CompetitionName LIKE 'A%' Limit 1)
    
ORDER BY T.TeamName;

```
