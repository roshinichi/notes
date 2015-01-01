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
	mysql> CREATE TABLE table_name(
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
- _Don't have multiple columns with the same sort of information_
- _Don't include multiple values in one cell._
- _Normalized Tables_

####Numeric Types
- `TINYINT` _127 to -128_
- `SMALLINT` _32768 to -32767_
- `MEDIUM INT` _8388608 to -8388608_	
- `INT` _2^31 to -2^31-1_
####String Types
- `ENUM` _a character string that has a limited number of total values, which must be defined_ e.g. `ENUM('M','F')`
- `SET` _a list of legal possible character strings. Unlike `ENUM`, a SET can contain multiple values in comparison to the one legal value with ENUM._
####Date&Time Types
- `DATE` _YYYY-MM-DD_
- `TIME` _HH:MM:SS_
- `DATETIME` _YYYY-MM-DD HH:MM:SS_
- `TIMESTAMP` _YYYYMMDDHHMMSS_
- `YEAR` _YYYY_

###Filling a table
- `DESCRIBE table_name` _checks the table's order first!

```
mysql> INSERT INTO table_name VALUE
	-> (`string1`,`string2, //use " " if there's an error
	-> `string3`,
	-> 123, //an int
	-> NULL); //NULL represents the primary key value
mysql> SELECT * FROM table_name; //displays the table
//if add more values, just seperated by ()
```

###Foreign Key
- Used to **make references** to the Primary Key of another table
- The Foreign Key can have a different name from the Primary Key name
- The value of a Foreign Key can have the value of NULL
- A Foreign Key doesn't have to be unique

```
mysql> CREATE TABLE score(
	-> student_id INT UNSIGNED NOT NULL,
	-> event_id INT UNSIGNED NOT NULL,
	-> score INT NOT NULL,
	-> PRIMARY KEY(event_id,student_id));//combined event and score
	//studnet_id in the KEY assures it's unique
	//the combination makes it unique
mysql> CREATE TABLE absence(
	-> student_id INT UNSIGNED NOT NULL,
	-> date DATE NOT NULL,
	-> PRIMARY KEY(student_id,date));
mysql> DESCRIBE test;
mysql> ALTER TABLE test
	-> ADD maxscore INT NOT NULL AFTER type;
mysql> INSERT INTO test VALUES
	-> ('2014-8-25','Q',15,1,NULL),
	->  ('2014-8-26','T',15,1,NULL);
```