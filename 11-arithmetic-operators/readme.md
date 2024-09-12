/*
  Arithmetic Operators
*/

```
SELECT (2 *  2) + 100;

SELECT 20 / 2;

SELECT 20 DIV 2;

SELECT 21 % 2;

SELECT name, days AS DaysOfWork, dayrate AS DayRate FROM `try`;

SELECT name, days AS DaysOfWork, dayrate AS DayRate, days * dayrate AS NeededMoney FROM `try`;

SELECT name, days AS DaysOfWork, dayrate AS DayRate, (days * dayrate) + 100 AS NeededMoney FROM `try`;

SELECT
  name,
  days AS DaysOfWork,
  dayrate AS DayRate,
  (days * dayrate) AS NeededMoney,
  (days * dayrate) + 100 AS NeededMoneyWithBonus
FROM
  `try`

SELECT
  name,
  days AS DaysOfWork,
  dayrate AS DayRate,
  (days * dayrate) AS NeededMoney,
  (days * dayrate) + 100 AS NeededMoneyWithBonus,
  (days * dayrate) + 100 - 50 AS ResultMoneyWithOfficeBoyMoney
FROM
  `try`
```