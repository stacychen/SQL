

## Goal: Count the number of submissions from each user.

The output consists of two columns: the first column displays user ID and the second column displays the number of submissions made by that user.

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
