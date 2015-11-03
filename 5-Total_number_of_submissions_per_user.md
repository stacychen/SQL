

## Goal: count the number of submissions from each user.

* Tables used: Users, Submissions
---
SQL Query code:
```
SELECT u.ID, COUNT(s.SubmittedUserID) AS 'Number of Submissions'
    FROM users u
JOIN submissions s  ON u.ID = s.SubmittedUserID
GROUP BY u.ID
ORDER BY u.ID
```
---
