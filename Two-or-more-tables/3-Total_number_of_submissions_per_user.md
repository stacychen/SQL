

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

```
GROUP BY u.ID
ORDER BY u.ID
```
* The above code will group all the identical user ID numbers together and then count the number of submissions associated with that particular user ID. The ORDER BY statement will list the user IDs in ascending order.

Run this code [here](https://www.kaggle.com/lochleven/d/kaggle/meta-kaggle/competition-list1/edit)
