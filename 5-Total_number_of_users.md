
## Goal: List all competitions and their number of users 

```
SELECT c.CompetitionName, COUNT(UserID) AS 'Number of Users'
    FROM Competitions AS c
JOIN Teams AS t
    ON c.ID = t.CompetitionID
JOIN TeamMemberships AS tm
    ON t.ID = tm.TeamID

GROUP BY CompetitionName
ORDER BY CompetitionName
```
