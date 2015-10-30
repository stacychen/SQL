
## Goal: List the competitions in the order of their prize value

Create a list

Table used: Competitions

---
```
SELECT CompetitionName, RewardQuantity
  FROM Competitions
WHERE RewardQuantity IS NOT NULL
ORDER BY RewardQuantity DESC

```
---
