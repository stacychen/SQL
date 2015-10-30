
## Goal: List the competitions in the order of their prize value

Create a list with all the competition names. List the competition names in the order of their prize value. 

Table used: Competitions

---
SQL Query code:
```
SELECT CompetitionName, RewardQuantity
  FROM Competitions
WHERE RewardQuantity != ''
ORDER BY RewardQuantity DESC

```
---

##### Notes:
```
SELECT CompetitionName, RewardQuantity
  FROM Competitions
```
* The above code will select the **CompetitionName** and **RewardQuantity** columns from the **Competitions** table. 

```
WHERE RewardQuantity != ''
```
* The above code is a conditions statement. This statement will excludes any competitions where the prize is not entered.

```
ORDER BY RewardQuantity DESC
```
*The above code will display the competition according to the prize value, in descending order. The competition with the highest prize value will be listed first.


[See Results here!](https://www.kaggle.com/lochleven/meta-kaggle/competition-list1/run/97102/files)
