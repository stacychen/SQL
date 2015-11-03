

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
```
SELECT u.ID, COUNT(s.SubmittedUserID) AS 'Number of Submissions'
    FROM users u
JOIN submissions s  ON u.ID = s.SubmittedUserID
```

* The above code will select the **ID** column from the **Users** table. The code will also count the total number of submissions that is associated with each user ID. The column that displays the number of user submissions will be renamed as **Number of Submissions**.
* The alias **u** is used for the table **Users** and the alias **s** is used for the table **Submissions**.
* The **Users** table will be joined with the **Submissions** table by matching **ID** in **Users** with **SubmittedUserID** in **Submissions**.


[See results here!](https://www.kaggle.com/lochleven/meta-kaggle/competition-list1/run/99042)
