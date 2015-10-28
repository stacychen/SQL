

## Goal: count the number of submissions from each user

```
SELECT u.ID, COUNT(s.SubmittedUserID)
    FROM users u
JOIN submissions s  ON u.ID = s.SubmittedUserID
GROUP BY u.ID
ORDER BY u.ID
```

