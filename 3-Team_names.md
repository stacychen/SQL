
## Goal: List all the teams names for a single competition.

Create a list with all the team names for a single competition. Here, the competition will be the first competition with a name that begins with the letter 'A'. The team names will be listed in alphabetical order.

Tables used: Competitions, Teams

```
SELECT C.CompetitionName, T.TeamName
    FROM Competitions AS C
        JOIN Teams AS T ON C.Id = T.CompetitionId
WHERE CompetitionName = (SELECT CompetitionName FROM Competitions WHERE CompetitionName LIKE 'A%' Limit 1)
ORDER BY T.TeamName
;
```
