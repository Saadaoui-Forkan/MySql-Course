1. Deal With Databases
```
/* Create Database elzero */
CREATE DATABASE elzero;

/* Show All Databases */
SHOW DATABASES;

/* Switch To This Database */
USE elzero;

/* Show Databases Like elzero */
SHOW DATABASES LIKE 'elzero';
```

2. Create Drop ShowStatus
```
/* Create Table With 3 Fields */
Create TABLE students (
  id int(11),
  name varchar(255),
  email varchar(255)
);

/* Show Columns Inside Table */

DESCRIBE students; # Shortcut For => SHOW COLUMNS FROM table_name;

DESC students; # Short For DESCRIBE

EXPLAIN students; # Same As Describe

SHOW COLUMNS FROM students; # Same As Previous Results

SHOW FIELDS FROM students; # Same As Previous Results

/* Show The Status Of The Tables */

SHOW TABLE STATUS;
```

3. Rename Change Types
```
/* Rename Multiple Tables */
RENAME TABLE s1 TO new1, s2 TO new2;

/* Change Table Engine */
ALTER TABLE new1 ENGINE = MYISAM;
```

3. Alter
```
/* Add New Password Field */
ALTER TABLE students ADD password varchar(255);

/* Add Username Field After name Field */
ALTER TABLE students ADD username varchar(255) AFTER name;

/* Add test Field As First Field */
ALTER TABLE students ADD test varchar(255) FIRST;

/* Delete Field last */
ALTER TABLE student DROP last;

/* Change Field Location And Type */
ALTER TABLE students CHANGE username username varchar(255) AFTER email;

/* Change Field Type */
ALTER TABLE students CHANGE test test char(50);

/* Modify Field Type */
ALTER TABLE students MODIFY test varchar(255);
```

4. Advanced
```
/* Change Table Name */
ALTER TABLE new1 RENAME osama;

/* Change Many Fields Name And Type */
ALTER TABLE students MODIFY username char(50), CHANGE id userid int(11);

/* Change Many Fields Name And Type */
ALTER TABLE students MODIFY username varchar(255), CHANGE userid id tinyint(1);

/* Change Character Set UTF-8 */
ALTER TABLE students CONVERT TO CHARACTER SET utf8;

/* Change Character Set Latin 1 */
ALTER TABLE students CONVERT TO CHARACTER SET latin1;
```