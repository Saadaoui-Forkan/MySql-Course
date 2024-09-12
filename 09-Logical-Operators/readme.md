```
/*
  Comparison Operators
  AND, &&
  NOT, !
  ||, OR
  XOR
*/

SELECT * FROM `try` WHERE `name` LIKE '%sama' AND `number` > 100;

SELECT * FROM `try` WHERE `name` LIKE '%sama' AND `number` < 10;

SELECT * FROM `try` WHERE NOT `name` LIKE '%sama';

SELECT * FROM `try` WHERE `name` LIKE '%sama' OR `number` > 100;

SELECT * FROM `try` WHERE `name` LIKE '%sama' XOR `number` < 10;

SELECT * FROM `try` WHERE `name` LIKE '%xxxx' XOR `number` > 100;
```