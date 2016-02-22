
## Goal: List all competitions and their number of users.

Create a table with two columns, with the first column listing the names of all the compeition and the second column listing the number of users participating in the named competition.

Tables used: Competitions, Teams, TeamMemberships

---
```
SELECT 
    c.CompetitionName, 
    COUNT(UserID) AS 'Number of Users'
FROM 
    Competitions AS c
JOIN 
    Teams AS t ON c.ID = t.CompetitionID
JOIN 
    TeamMemberships AS tm ON t.ID = tm.TeamID
GROUP BY CompetitionName
ORDER BY CompetitionName
;
```
---

##### Notes:

```
SELECT 
    c.CompetitionName, 
    COUNT(UserID) AS 'Number of Users'
FROM 
    Competitions AS c
JOIN 
    Teams AS t ON c.ID = t.CompetitionID
JOIN 
    TeamMemberships AS tm ON t.ID = tm.TeamID
```
* The above code will select the **CompetitionName** column from the **Competitions** table. The code will also count the number of user IDs that is associated for the selected competition. The column that displays the number of user IDs will be renamed as **Number of Users**.
* The alias **c** is used for the table **Competitions**, the alias **t** is used for the table **Teams**, and the alias **tm** is used for the table **TeamMemberships**.
* The **Competitions** table will be joined with the **Teams** table by matching **ID** in **Competitions** with **CompetitionID** in **Teams**.

```
GROUP BY CompetitionName
ORDER BY CompetitionName
```
* The above code will group all the identical competition names together and then count the number of user IDs associated with that particular competition. The *ORDER BY* statement will list the compeitions in alphabetical order.

* The **TeamMemberships** table will be joined with the **Teams** table by matching **ID** in **Teams** with **TeamID** in **TeamMemberships**.

Run this code [here](https://www.kaggle.com/lochleven/d/kaggle/meta-kaggle/competition-list1/edit)
