
## Goal: List all competitions and their number of users 

* The first column lists all the competition names and the second column lists the total number of users for each competition.
* Tables used: Competitions, Teams, TeamMemberships

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
