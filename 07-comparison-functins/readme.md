1. Between and Not between
```
/*
  Between
  number => Field Name
  date => Field Name
*/

SELECT * FROM `try` WHERE number BETWEEN 2 AND 6;

SELECT * FROM `try` WHERE date BETWEEN '2016-05-18' AND '2016-05-25';

SELECT
  *
FROM
  `try`
WHERE
  date
BETWEEN
  DATE_SUB(CURDATE(), INTERVAL 2 MONTH)
AND
  CURDATE();

SELECT
  *
FROM
  `try`
WHERE
  date
BETWEEN
  DATE_SUB(CURDATE(), INTERVAL 1 YEAR)
AND
  CURDATE();

/*
  Not Between
  number => Field Name
  date => Field Name
*/

SELECT * FROM `try` WHERE number NOT BETWEEN 2 AND 6;
```

2. In And Not In
```
/*
  In
  number => Field Name
  date => Field Name
*/

SELECT * FROM `try` WHERE number IN (4, 5, 8);

SELECT * FROM `try` WHERE number IN (4, 5, 8, 'Osama', 100);

SELECT * FROM `try` WHERE date IN ('2016-05-25', '2016-05-18');

/*
  Not In
  number => Field Name
  date => Field Name
*/

SELECT * FROM `try` WHERE number NOT IN (3, 7);

SELECT * FROM `try` WHERE date NOT IN ('2016-07-16');
```

3. Like And Not Like
```
/*
  Like
  name => Field Name
*/

SELECT * FROM `try` WHERE name = 'Osama';

SELECT * FROM `try` WHERE name LIKE 'Osama';

SELECT * FROM `try` WHERE name LIKE '%sama'; # % => Empty Or Collection Of Characters

SELECT * FROM `try` WHERE name LIKE '%ama'; # % => Empty Or Collection Of Characters

SELECT * FROM `try` WHERE name LIKE '%ama%';

SELECT * FROM `try` WHERE name LIKE '%i%';

SELECT * FROM `try` WHERE name LIKE 'Z%o';

SELECT * FROM `try` WHERE name LIKE '%a%a%';

SELECT * FROM `try` WHERE name LIKE '_sama'; # _ => One Character

SELECT * FROM `try` WHERE name LIKE 'Sam_h'; # _ => One Character

SELECT * FROM `try` WHERE name LIKE '%m_h';

SELECT * FROM `try` WHERE name LIKE '%_h';

SELECT * FROM `try` WHERE name LIKE '%_%';

/*
  Not Like
  name => Field Name
*/

SELECT * FROM `try` WHERE name NOT LIKE '%sama';
```