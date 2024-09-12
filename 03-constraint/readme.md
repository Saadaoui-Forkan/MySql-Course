1. Intro
```
/* Make Username Not Null */
ALTER TABLE students MODIFY username varchar(255) NOT NULL;

/* Add osama Not Null */
ALTER TABLE students ADD osama varchar(255) NOT NULL;
```

2. Not Null | Unique
```
/* NOT NULL ==> empty or with value */

/* Make Username Unique */
ALTER TABLE students ADD UNIQUE(username);

/* Drop Index For osama */
ALTER TABLE students DROP INDEX osama;

/* Add test Field Not Null And Unique */
ALTER TABLE students ADD test varchar(255) NOT NULL UNIQUE;
```

3. Primary Key
```
/*
* Only one in table
*/

/* Create Table classes With Two Fields */
CREATE TABLE classes (
    cid int NOT NULL PRIMARY KEY,
    name varchar(255) UNIQUE
);

/* Create Table teachers With 3 Fields */
CREATE TABLE teachers (
    tid int NOT NULL,
    name varchar(255),
    PRIMARY KEY(tid)
);

/* Make students id field Primary Key */
ALTER TABLE students ADD PRIMARY KEY(id);

/* Drop Primary Key From students Table */
ALTER TABLE students DROP PRIMARY KEY;

/* Get Table Indexs */
SHOW INDEXES FROM students;
```

4. Foreign Key
```
/*
* Foreign أجنبي -  something that is from or related to another
* Used in relationship between tables
*/

/* Create Table clients With 3 Fields */
CREATE TABLE clients (
    id INT NOT NULL,
    username varchar(255) UNIQUE,
    email varchar(255) UNIQUE,
    PRIMARY KEY(id)
) ENGINE = INNODB;

/* Create Table orders With 3 Fields */
CREATE TABLE orders (
    order_id INT NOT NULL,
    price varchar(255),
    client_id INT NOT NULL,
    PRIMARY KEY(order_id),
    FOREIGN KEY(client_id) REFERENCES clients(id)
) ENGINE = INNODB;

/*
    * CASCADE: update and ensure automatic synchronization modifications between parent table and child table.
    * 
    ALTER TABLE orders
    ADD CONSTRAINT ordering
    FOREIGN KEY(client_id) REFERENCES clients(id)
    ON UPDATE CASCADE
    ON DELETE CASCADE;
*/

Foreign Key Types
- one to one
- one to many
- many to many
```