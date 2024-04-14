# SQL-CheatSheet


**DDL** is short name of Data Definition Language, which deals with database schemas and descriptions, of how the data should reside in the database.

**DCL** is short name of Data Control Language which includes commands such as GRANT, and mostly concerned with rights, permissions and other controls of the database system.

**DML** is short name of Data Manipulation Language which deals with data manipulation, and includes most common SQL statements such INSERT, UPDATE, DELETE etc, and it is used to store, modify, delete and update data in database.

**DQL** is short name of Data Query Language which used for performing queries on the data within schema objects. The purpose of the DQL Command is to get some schema relation based on the query passed to it. SELECT statement is used to retrieve data from the database.

# Datatypes

#### Text types

| Data type        | Description                                                                                                                                                                                                                                                                                      |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CHAR(size)       | Holds a fixed length string (can contain letters, numbers, and special characters). The fixed size is specified in parenthesis. Can store up to 255 characters                                                                                                                                   |
| VARCHAR(size)    | Holds a variable length string (can contain letters, numbers, and special characters). The maximum size is specified in parenthesis. Can store up to 255 characters. Note: If you put a greater value than 255 it will be converted to a TEXT type                                               |
| TINYTEXT         | Holds a string with a maximum length of 255 characters                                                                                                                                                                                                                                           |
| TEXT             | Holds a string with a maximum length of 65,535 characters                                                                                                                                                                                                                                        |
| BLOB             | For BLOBs (Binary Large OBjects). Holds up to 65,535 bytes of data                                                                                                                                                                                                                               |
| MEDIUMTEXT       | Holds a string with a maximum length of 16,777,215 characters                                                                                                                                                                                                                                    |
| MEDIUMBLOB       | For BLOBs (Binary Large OBjects). Holds up to 16,777,215 bytes of data                                                                                                                                                                                                                           |
| LONGTEXT         | Holds a string with a maximum length of 4,294,967,295 characters                                                                                                                                                                                                                                 |
| LONGBLOB         | For BLOBs (Binary Large OBjects). Holds up to 4,294,967,295 bytes of data                                                                                                                                                                                                                        |
| ENUM(x,y,z,etc.) | Let you enter a list of possible values. You can list up to 65535 values in an ENUM list. If a value is inserted that is not in the list, a blank value will be inserted.Note: The values are sorted in the order you enter them.You enter the possible values in this format: ENUM('X','Y','Z') |
| SET              | Similar to ENUM except that SET may contain up to 64 list items and can store more than one choice                                                                                                                                                                                               |

#### Number types

| Data type       | Description                                                                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| TINYINT(size)   | -128 to 127 normal. 0 to 255 UNSIGNED*. The maximum number of digits may be specified in parenthesis                                                                                                                                  |
| SMALLINT(size)  | -32768 to 32767 normal. 0 to 65535 UNSIGNED*. The maximum number of digits may be specified in parenthesis                                                                                                                            |
| MEDIUMINT(size) | -8388608 to 8388607 normal. 0 to 16777215 UNSIGNED*. The maximum number of digits may be specified in parenthesis                                                                                                                     |
| INT(size)       | -2147483648 to 2147483647 normal. 0 to 4294967295 UNSIGNED*. The maximum number of digits may be specified in parenthesis                                                                                                             |
| BIGINT(size)    | -9223372036854775808 to 9223372036854775807 normal. 0 to 18446744073709551615 UNSIGNED*. The maximum number of digits may be specified in parenthesis                                                                                 |
| FLOAT(size,d)   | A small number with a floating decimal point. The maximum number of digits may be specified in the size parameter. The maximum number of digits to the right of the decimal point is specified in the d parameter                     |
| DOUBLE(size,d)  | A large number with a floating decimal point. The maximum number of digits may be specified in the size parameter. The maximum number of digits to the right of the decimal point is specified in the d parameter                     |
| DECIMAL(size,d) | A DOUBLE stored as a string , allowing for a fixed decimal point. The maximum number of digits may be specified in the size parameter. The maximum number of digits to the right of the decimal point is specified in the d parameter |

#### Date types

| Data type   | Description                                                                                                                                                                                                                              |
|-------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DATE()      | A date. Format: YYYY-MM-DDNote: The supported range is from '1000-01-01' to '9999-12-31'                                                                                                                                                 |
| DATETIME()  | *A date and time combination. Format: YYYY-MM-DD HH:MI:SSNote: The supported range is from '1000-01-01 00:00:00' to '9999-12-31 23:59:59'                                                                                                |
| TIMESTAMP() | *A timestamp. TIMESTAMP values are stored as the number of seconds since the Unix epoch ('1970-01-01 00:00:00' UTC). Format: YYYY-MM-DD HH:MI:SSNote: The supported range is from '1970-01-01 00:00:01' UTC to '2038-01-09 03:14:07' UTC |
| TIME()      | A time. Format: HH:MI:SSNote: The supported range is from '-838:59:59' to '838:59:59'                                                                                                                                                    |
| YEAR()      | A year in two-digit or four-digit format.Note: Values allowed in four-digit format: 1901 to 2155. Values allowed in two-digit format: 70 to 69, representing years from 1970 to 2069                                                     |
#### Arithmetic Operators

|Operator|Description
|--------|---------|
| +      | Add
| -      | Subtract
| *      | Multiply
| /      | Divide
| %      | Modulo
#### Bitwise Operator
|Operator|Description
|--------|---------|
| &      | Bitwise AND
| \|      | Bitwise OR
| ^      | Bitwise exclusive OR
#### Comparison Operators
|Operator|Description|
|--------|---------|
|=    | Equal to|
|\>   | Greater than|
|<    | Less than|
|= | Greater than or equal to |
|<= | Less than or equal to |
|<> | Not equal to |
|LIKE ‘%expression%’ | Contains ‘expression’ |
|IN (‘exp1’, ‘exp2’, ‘exp3’) | Contains any of ‘exp1’, ‘exp2’, or ‘exp3’ |

#### Wildcard Characters
In SQL, Wildcards are special characters used with the LIKE and NOT LIKE keywords which allow
us to search data with sophisticated patterns much more efficiently

| Name   | Description                                                                                                                                                                                                                              |
|-------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| %      | Equates to zero or more characters. Example 1: Find all users with surnames ending in ‘son’. ```SELECT * FROM users WHERE surname LIKE '%son';``` Example 2: Find all users living in cities containing the pattern ‘che’ ```SELECT * FROM users WHERE city LIKE '%che%';``` |
| _      | Equates to any single character. Example: Find all users living in cities beginning with any 3 characters, followed by ‘chester’. ```SELECT * FROM users WHERE city LIKE '___chester';```|
| [charlist]      | Equates to any single character in the list. Example 1: Find all users with first names beginning with J, H or M. ```SELECT * FROM users WHERE first_name LIKE '[jhm]%';``` Example 2: Find all users with first names beginning letters between A–L. ```SELECT * FROM users WHERE first_name LIKE '[a-l]%';``` Example 3: Find all users with first names not ending with letters between n–s. ```SELECT * FROM users WHERE first_name LIKE '%[!n-s]';```|

#### Complete Set In SQL

| Relational Algebra | SQL                                                          |
| --------- | ----------------------- |
| **Π𝑠(R)** | ```SELECT DISTINCT s FROM R;```	|
| **𝜎𝗉(R)** | ```SELECT * FROM R WHERE p;``` |
| **R×S** | ```SELECT * FROM R,S;``` |
| **R-S** | ```SELECT column(s) FROM R WHERE NOT EXISTS (SELECT column(s) FROM S);``` We can also use ```EXCEPT``` to achieve set difference. |
| **R∪S** | ```SELECT column(s) FROM R UNION SELECT column(s) FROM S;``` |


## Working On A DataBase


## Login

```bash
mysql -u root -p
```

## Show Users

```sql
SELECT User, Host FROM mysql.user;
```

## Create User

```sql
CREATE USER 'someuser'@'localhost' IDENTIFIED BY 'somepassword';
```

## Grant All Priveleges On All Databases

```sql
GRANT ALL PRIVILEGES ON * . * TO 'someuser'@'localhost';
FLUSH PRIVILEGES;
```

## Show Grants

```sql
SHOW GRANTS FOR 'someuser'@'localhost';
```

## Remove Grants

```sql
REVOKE ALL PRIVILEGES, GRANT OPTION FROM 'someuser'@'localhost';
```

## Delete User

```sql
DROP USER 'someuser'@'localhost';
```

## Exit

```sql
exit;
```

## Show Databases

```sql
SHOW DATABASES
```

## Create Database

```sql
CREATE DATABASE test_database;
```

## Delete Database

```sql
DROP DATABASE test_database;
```

## Select Database

```sql
USE test_database;
```

#### Table

In the below example, data passed to the id column must be an int, whilst the first_name column
has a VARCHAR data type with a maximum of 255 characters.

```sql
CREATE TABLE users (
	id int,
	first_name varchar(255)
);
```

Check if not exist and create

```sql
IF object_id('tbl_customer', n'U') IS NOT NULL DROP TABLE tbl_customer;
GO 
CREATE TABLE tbl_customer ( id_customer INT NOT NULL PRIMARY key, fi_moral_nr INT, name VARCHAR(25) NOT NULL, vorname VARCHAR NOT NULL, wohnort VARCHAR );
GO
```

#### Alter Table
`Adds, deletes or edits columns in a table`. It can also be used to add and
delete constraints in a table, as per the above.
Example: Adds a new boolean column called ‘approved’ to a table named
‘deals’.

```sql
ALTER TABLE deals
ADD approved boolean;
```
Example 2: Deletes the ‘approved’ column from the ‘deals’ table
```sql
ALTER TABLE deals
DROP COLUMN approved;
```
#### Primary Key
Alter an existing table and set the primary key to the first_name column.
```sql
ALTER TABLE stud
ADD PRIMARY KEY (first_name);
```

#### Alter Column
Changes the data type of a table’s column.
Example: In the ‘users’ table, make the column ‘incept_date’ into a
‘datetime’ type.

```sql
ALTER TABLE users
ALTER COLUMN incept_date datetime;
```

#### Drop Column
Deletes a column from a table.
Example: Removes the first_name column from the users table.

```sql
ALTER TABLE users
DROP COLUMN first_name
```

