
### Goal: Calculate the average number of submissions per competition for each individual user

Tables used: Users, TeamMemberships, Submissions

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
    users u
JOIN 
    teamMemberships tm ON tm.UserID = u.ID
JOIN 
    (SELECT submittedUserID, count(submittedUserID) AS 'Submissions' 
            FROM submissions s 
            JOIN users u on s.submittedUserID = u.id GROUP BY u.id) sb
            ON u.ID = sb.submittedUserID
GROUP BY u.displayname
ORDER BY 1 DESC
;
```
---
##### Notes:

* Line 17: The code will select the **displayname** column from the **users** table. 
* Line 18: The code will also count the number of TeamIDs that is associated for each username. The column that displays the number of TeamIDs will be renamed as **Competitions**. This is the number of competitions the user participated in. 
* Line 19: This code will count the number of submissions the users has submitted across all compeitions. 
* Line 20: This column will calculate the average number of submissions the users have made, by dividing the third column by the second column. 
* The alias **u** is used for the table **users**, the alias **tm** is used for the table **teamMemberships**, and the alias **s** is used for the table **submissions**.
* The **users** table will be joined with the **teamMemberships** table by matching **ID** in **users** with **userID** in **teamMemberships**.
* Line 26-29: These lines will count the number of subissions for each user. This is done by: joining the **users** table with **submissions** table by matching **ID** in users with **submittedUserID** in **submissions**. This newly created table will know as **sb** that consists of two columns: **submittedUserID** and **submissions** - providing the number of submissions for each user ID. The **submissions** column counts the number of submissions per userID. 
* Line 25: the **users** table is joined with the **sb** table by matching **ID** in **user** with **submittedUserID** in **sb**. 
* Line 30-31: The GROUP BY statement will group all the identical user names together. The ORDER BY statement will list all the usernames in alphabetical order.

Run this code [here](https://www.kaggle.com/lochleven/d/kaggle/meta-kaggle/competition-list1/edit)

