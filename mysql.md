#12/30/14
***
##MySQL Notes
- Log into MySQL thru SSH
	
	```
	mysql -h 127.0.0.1 -u root -p
	```
- `show databases;` shows databases
- **commands in MySQL are all UPPERCASE**
- `CREATE DATABASE database_name;` creates a database, don't drop `;`
- `USE database_name;` selects a database
- `SELECT DATABASE();` shows the currently selecting databse
- `DROP DATABASE IF EXISTS database_name;` destroys a database

	```
	CREATE TABLE database_name(
	-> xxx VARCHAR(30) NOT NULL,
	-> xxx VARCHAR(30) NOT NULL,
	-> state CHAR(2) NOT NULL DEFAULT "CA","
	-> zip MEDIUMINT UNSIGHED NOT NULL,
	-> birth_date DATE NOT NULL,
	-> sex ENUM('M','F') NOT NULL,
	-> date_entered TIMESTAMP,
	-> lunch_cost FLOAT NULL,
	-> student_id INT UNSIGHED NOT NULL AUTO_INCREMENT PRIMARY KEY;
	)
	```
	
- **_`AUTO_INCREMENT`_** _automatically increments after each object is created_
- **_`PRIMARY KEY`_** _creates unit identity for each object_
- `SHOW TABLES` _shows the table that being created_

###Primary Key
- Uniquely identifies a row or record
- Each Primary Key must be **unique** to the row
- Must be given a value when the row is created and  that value can't be NULL
- The original value can't be changed
- It's probably best to auto increment the value of the key

###Atomic Tables & Table Templating
- Every table should focus on describing just 1 thing
- After you decide what one thing your table will describe, then decide what things you need to describe that thing
- Write out all the ways to describe the thing and if any of those things requires multiple inputs, pull them out