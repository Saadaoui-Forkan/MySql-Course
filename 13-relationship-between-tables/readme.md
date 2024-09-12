1. Group, Order And Having
```
SELECT * FROM `contribution` ORDER BY `name`;

SELECT * FROM `contribution` ORDER BY `name`, `points`;

SELECT * FROM `contribution` GROUP BY `name`;

SELECT name, points FROM `contribution` GROUP BY `name`;

SELECT name, SUM(points) FROM `contribution` GROUP BY `name`;

SELECT name, SUM(points) FROM `contribution` GROUP BY `name` ORDER BY points;

SELECT name, SUM(points) FROM `contribution` GROUP BY `name` ORDER BY points DESC;

SELECT status FROM `orders` ORDER BY status;

SELECT status, COUNT(status) How_Much FROM `orders` GROUP BY status ORDER BY status;

SELECT status, COUNT(status) How_Much FROM `orders` GROUP BY status HAVING How_Much > 1;
```

2. Simulation Of Join
```
CREATE TABLE (
  user_id INT NOT NULL AUTO_INCREMENT,
  user_name varchar(255),
  lang_id INT NOT NULL,
  PRIMARY KEY (user_id),
  FOREIGN KEY (lang_id) REFERENCES langs(lang_id)
) ENGINE = INNODB;

SELECT * FROM `users`, `langs`;

SELECT * FROM `users`, `langs` WHERE users.lang_id = langs.lang_id;
```

3. Aliases In Deep
```
SELECT
  users.lang_id
FROM
  `users`, `langs`
WHERE
  users.lang_id = langs.lang_id;

SELECT
  users.user_id
FROM
  `users`, `langs`
WHERE
  users.lang_id = langs.lang_id;

SELECT
  users.user_id,
  users.user_name,
  langs.lang_name
FROM
  `users`, `langs`
WHERE
  users.lang_id = langs.lang_id;

SELECT
  u.user_id User_Id,
  u.user_name Username,
  l.lang_name Fav_Lang
FROM
  `users` u,
  `langs` l
WHERE
  u.lang_id = l.lang_id;

SELECT
  u.user_id,
  u.user_name,
  l.lang_name
FROM
  `users` u,
  `langs` l
WHERE
  u.lang_id = l.lang_id;
```

4. join
```
/*
  Inner Join
*/

SELECT
  u.user_id,
  u.user_name,
  l.lang_name
FROM
  `users` u
INNER JOIN
  `langs` l
ON
  u.lang_id = l.lang_id;

/*
  Left And Right Join
*/

SELECT
  u.user_id,
  u.user_name,
  l.lang_name
FROM
  `users` u
INNER JOIN
  `langs` l
ON
  u.lang_id = l.lang_id;

SELECT
  u.user_id,
  u.user_name,
  l.lang_name
FROM
  `users` u
LEFT JOIN
  `langs` l
ON
  u.lang_id = l.lang_id;

SELECT
  u.user_id,
  u.user_name,
  l.lang_name
FROM
  `users` u
RIGHT JOIN
  `langs` l
ON
  u.lang_id = l.lang_id;

SELECT
  l.lang_name,
  COUNT(l.lang_id) How_Much_Used
FROM
  `users` u
INNER JOIN
  `langs` l
ON
  u.lang_id = l.lang_id;
GROUP BY
  l.lang_id
```