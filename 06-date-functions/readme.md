1. CurTime, CurDate, Now
```
/*
  Get Current Time
  HH:MM:SS
*/

SELECT CURTIME();
SELECT CURRENT_TIME();
SELECT CURRENT_TIME;

/*
  Get Current Date
  YYYY-MM-DD
*/

SELECT CURDATE();
SELECT CURRENT_DATE();
SELECT CURRENT_DATE;

/*
  Get Current Date & Time
  YYYY-MM-DD HH:MM:SS
*/

SELECT NOW();
SELECT CURRENT_TIMESTAMP();
SELECT CURRENT_TIMESTAMP;
```

2. Day, DayName
```
/*
  Select Day Name
  Day Name
  Day Of Week
  Day Of Month
  Day Of Year
*/

SELECT CURDATE() AS Today, DAYNAME(CURDATE()) AS TodayName;

SELECT CURDATE() AS Today, DAYNAME('2016-07-30') AS TodayName;

SELECT name, date, DAYNAME(date) FROM `try`;

SELECT name, date, DAYNAME(date), DAYOFMONTH(date) FROM `try`;

SELECT name, date, DAYNAME(date), DAYOFMONTH(date), DAYOFWEEK(date) FROM `try`;

SELECT name, date, DAYNAME(date), DAYOFMONTH(date), DAYOFWEEK(date), DAYOFYEAR(date) FROM `try`;
```

3. Month, Hour, Minute
```
/*
  Select Month
  Month
  Month Name
  Hour
  Minute
*/

SELECT date, MONTH(date) FROM `try`;

SELECT date, MONTH(date), MONTHNAME(date) FROM `try`;

SELECT date, MONTH(date), MONTHNAME(date), HOUR(date) FROM `try`;

SELECT date, MONTH(date), MONTHNAME(date), HOUR(date), MINUTE(date) FROM `try`;
```

4. Date Diff + Examples
```
/*
  Select Date Different
  DATEDIFF(Date1, Date2)
*/

SELECT id, name, date, DATEDIFF(CURRDATE(), date) AS NumberOfDayes FROM `try`;

SELECT
  id, name, date,
  CONCAT('Registered ', DATEDIFF(CURRDATE(), date), ' Days Ago.') AS NumberOfDayes
FROM
  `try`;
```

4. Date Add, Date Sub, Last Day
```
/*
  Last Day
  LAST_DAY(Date)
*/

SELECT name, date, LAST_DAY(date) FROM `try`;

SELECT name, date, LAST_DAY(date), DAYNAME(LAST_DAY(date)) FROM `try`;

/*
  Date Add
  DATE_ADD(Date, Interval Expression Time Unit)
*/

UPDATE `try` SET date = DATE_ADD(date, INTERVAL 10 DAY);

UPDATE `try` SET date = DATE_ADD(date, INTERVAL 1 MONTH);

/*
  Date Sub
  DATE_SUB(Date, Interval Expression Time Unit)
*/

UPDATE `try` SET date = DATE_SUB(date, INTERVAL 1 MONTH);
```