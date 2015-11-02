

## Goal: Calculate the number of teams for one competition.

The goal is to calculate the number of teams for one selected competition. Here, the competition selected will be the first competition with a name that begins with the letter 'H'. 

```
SELECT C.CompetitionName, COUNT(T.TeamName)
  FROM Competitions C
JOIN Teams T ON C.Id = T.CompetitionId
  WHERE CompetitionName IN (SELECT CompetitionName FROM Competitions 
                            WHERE CompetitionName LIKE 'H%' 
                            ORDER BY CompetitionName LIMIT 1)
;
```
##### Notes:

```
SELECT C.CompetitionName, COUNT(T.TeamName)
  FROM Competitions C
JOIN Teams T ON C.Id = T.CompetitionId  
```
* The above code will select the **CompetitionName** column from the **Competitions** table. The code will also count the number of teams that is associated for the selected competition. 
* The alias **C** is used for the table **Competitions** and the alias **T** is used for the table **Teams**.
* The **Competitions** table will be joined with the **Teams** table by matching **ID** in **Competitions** with **CompetitionID** in **Teams**.

```
WHERE CompetitionName IN (SELECT CompetitionName FROM Competitions 
                            WHERE CompetitionName LIKE 'H%' 
                            ORDER BY CompetitionName LIMIT 1)
```
* The above code is a conditions statement. The code inside the parenthesis will search for all the competition names that begin with the letter 'H'. Then, the list of competition names will be listed in alphabetic order. The *LIMIT 1* statement will return only one competition name. The one competition name will be selected and the number of teams registered for the competition will be counted.


[See results here!](https://www.kaggle.com/lochleven/meta-kaggle/competition-list1/run/97821)
