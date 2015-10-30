
## Goal: List the competitions in the order of their prize value

Create a list with all the competition names. List the competition names in the order of their prize value. 

Table used: Competitions

---
SQL Query code:
```
SELECT CompetitionName, RewardQuantity
  FROM Competitions
WHERE RewardQuantity IS NOT NULL
ORDER BY RewardQuantity DESC

```
---

##### Notes:
```
SELECT CompetitionName, RewardQuantity
  FROM Competitions
```
The above code will select the *CompetitionName* and *RewardQuantity* columns from the *Competitions* table. 

```
WHERE RewardQuantity IS NOT NULL
```
The above code is a conditions statement. 
