

## Goal: Count the number of submissions from each user.

The output consists of two columns: the first column displays user ID and the second column displays the number of submissions made by that user.

* Tables used: Users, Submissions

---
SQL code:
```
SELECT u.ID, COUNT(s.SubmittedUserID) AS 'Number of Submissions'
    FROM users u
JOIN submissions s  ON u.ID = s.SubmittedUserID
GROUP BY u.ID
ORDER BY u.ID
```
---

##### Notes:


[See results here!](https://www.kaggle.com/lochleven/meta-kaggle/competition-list1/run/99042)
