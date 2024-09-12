/*
  If Condition
  IF(Condition, True, False)
*/

```
SELECT id, name, IF(number < 24, 'Hard Luck', 'Congratz') AS result FROM `try`;

SELECT id, name, IF(number < 24, CONCAT('Hard Luck', number), CONCAT('Congratz', number)) AS result FROM `try`;

UPDATE `try` SET `number` = IF(number < 1, number + 10, number)
```

/*
  Case
    When Expression = Value Then Result
    When Expression = Value Then Result
    When Expression = Value Then Result
  End

  Case Value
    When Value Then Result
    When Value Then Result
    When Value Then Result
    Else Result
  End
*/
```
SELECT
  id, name,
  CASE
    WHEN number = 10 THEN 'Not Bad'
    WHEN number = 15 THEN 'Good'
    WHEN number = 20 THEN 'Perfect'
    ELSE 'Unknown Rank'
  END AS result
FROM
  `try`;

SELECT
  id, name,
  CASE
    WHEN number > 10 THEN 'Good'
    WHEN number = 24 THEN 'Perfect'
    ELSE 'Unknown Rank'
  END AS result
FROM
  `try`;

SELECT
  id, name,
  CASE number
    WHEN 10 THEN 'Not Bad'
    WHEN 15 THEN 'Good'
    WHEN 20 THEN 'Perfect'
    ELSE 'Unknown Rank'
  END AS result
FROM
  `try`;

UPDATE `try` SET `number` =
CASE number
  WHEN 10 THEN number + 10
  WHEN 15 THEN number + 15
  WHEN 24 THEN number + 24
  ELSE number
END;
```