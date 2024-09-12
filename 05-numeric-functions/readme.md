1. Ceil, Floor, Round
```
/*
  Ceil => CEIL(Number)
  number => Field Name
*/

SELECT number AS MainNumber, CEIL(number) AS newNumber FROM `try`;

/*
  Floor => FLOOR(Number)
  number => Field Name
*/

SELECT number AS MainNumber, FLOOR(number) AS newNumber FROM `try`;

/*
  Round => ROUND(Number, Decimal)
  number => Field Name
*/

SELECT number AS MainNumber, ROUND(number) AS newNumber FROM `try`;

SELECT number AS MainNumber, ROUND(number, 2) AS newNumber FROM `try`;
```

2. Mod, Truncate, Pow
```
/*
  Truncate => TRUNCATE(Number, Decimal)
  number => Field Name
*/

SELECT
  number AS MainNumber,
  ROUND(number, 2) AS newNumber,
  TRUNCATE(number, 2)
FROM
  `try`;

INSERT INTO
  `test`.`try` (`id`, `number`)
VALUES
  (NULL, TRUNCATE('123456.65656565', 2));

/*
  Pow => POW(Number, Powered)
  number => Field Name
*/

SELECT POW(2, 3);

SELECT number, POWER(number, 2) FROM `try`;

/*
  Mod => MOD(Number, Mod)
  number => Field Name
*/

SELECT MOD(7, 2);
```