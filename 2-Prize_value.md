
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
