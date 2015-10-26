
## Goal: List all the teams (names) for one particular competition


```
SELECT Competitions.CompetitionName, Teams.TeamName
    FROM Competitions
JOIN Teams ON Competitions.Id = Teams.CompetitionId
    WHERE CompetitionName = (SELECT DISTINCT CompetitionName 
    FROM Competitions WHERE CompetitionName LIKE 'A%' Limit 1);

```
