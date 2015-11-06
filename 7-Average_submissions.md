
### Goal: Calculate the average number of submissions per competition for each individual user

* The first column lists the names of individual users.
* The second column lists the number of competitions each individual participates in.
* The third column lists the total number of submissions made by each individual user. 
* The fourth column lists the average number of submissions per competition made by each user. 

---
SQL code:

```
SELECT 
    u.displayname,  
    Count(tm.TeamID) AS 'Competitions',
    sb.submissions AS 'Submissions',
    sb.submissions/Count(tm.TeamID) AS 'Avg sub per competition'
FROM 
    teamMemberShips tm
INNER JOIN 
    users u ON tm.UserID = u.ID
INNER JOIN 
    (SELECT submittedUserID, count(submittedUserID) AS 'Submissions' 
            FROM submissions s 
            JOIN users u on s.submittedUserID = u.id GROUP BY u.id) sb
            ON u.ID = sb.submittedUserID
GROUP BY u.displayname
ORDER BY 1 DESC
```
---
