# `100 MySQL Exercises`

Written by: [Joseph Anthony Debono](https://github.com/jadebono).  
Email: [Joseph Debono](joe@jadebono.com).

These exercises have been adapted for MySQL, will use syntax specific to MySQL.

To return to the readme file: [README](./README.md).

---

## `General Practice Notes`

1. SQL syntax and keywords may differ from from one implementation to another of SQL;
1. Oracle and MySQL have quite similar syntax but there are some differences;
1. Commands in sql are called 'query'/'queries';
1. Indent using spaces to make your code clearer to read;
1. Use single quotes '' not double quotes "" to encapsulate strings and string-type data;
1. The semicolon ; is used to end a sequence of SQL commands or query. When the Relational Database Management System (RDMS) sees the ; it knows that the query terminates there and that there is nothing else outstanding;
1. Column names and groups of columns are separated by a comma , except the last one in a sequence;
1. Use underscores for spaces;
1. SQL is case insensitive but the convention is generally to use uppercase for SQL key words.

---

## `MySQL datatypes`

These are the main datatypes of MySQL:

### Character Datatypes

1. CHAR(size): Fixed-length character data of length size bytes.
1. VARCHAR(size): Variable-length character data with a maximum length of size bytes.
1. BINARY(size): Fixed-length binary data of length size bytes.
1. VARBINARY(size): Variable-length binary data with a maximum length of size bytes.
1. TINYBLOB: Very small binary data.
1. TINYTEXT: Very small text data.
1. BLOB(size): Binary Large Object, can store up to 65,535 bytes of binary data.
1. TEXT(size): Text data, can store up to 65,535 characters.
1. MEDIUMBLOB: Medium-sized binary data, can store up to 16,777,215 bytes.
1. MEDIUMTEXT: Medium-sized text data, can store up to 16,777,215 characters.
1. LONGBLOB: Large binary data, can store up to 4,294,967,295 bytes.
1. LONGTEXT: Large text data, can store up to 4,294,967,295 characters.

### Number Datatypes

1. TINYINT(size): Very small integer. The signed range is -128 to 127. The unsigned range is 0 to 255.
1. SMALLINT(size): Small integer. The signed range is -32,768 to 32,767. The unsigned range is 0 to 65,535.
1. MEDIUMINT(size): Medium-sized integer. The signed range is -8,388,608 to 8,388,607. The unsigned range is 0 to 16,777,215.
1. INT(size) or INTEGER(size): Standard integer. The signed range is -2,147,483,648 to 2,147,483,647. The unsigned range is 0 to 4,294,967,295.
1. BIGINT(size): Large integer. The signed range is -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807. The unsigned range is 0 to 18,446,744,073,709,551,615.
1. FLOAT(p): Floating-point number with a precision of p.
1. DOUBLE(size, d) or DOUBLE PRECISION(size, d): Double-precision floating-point number.
1. DECIMAL(size, d) or NUMERIC(size, d): Fixed-point number.

### Date/Time Datatypes

1. DATE: Date values (year, month, day).
1. DATETIME(fsp): Date and time values (year, month, day, hour, minute, second, fractional seconds).
1. TIMESTAMP(fsp): Timestamp values (year, month, day, hour, minute, second, fractional seconds), with the addition of timezone handling.
1. TIME(fsp): Time values (hour, minute, second, fractional seconds).
1. YEAR: Year values.

### Large Object (LOB) Datatypes

1. TINYBLOB: Very small binary data.
1. BLOB(size): Binary Large Object, can store up to 65,535 bytes of binary data.
1. MEDIUMBLOB: Medium-sized binary data, can store up to 16,777,215 bytes.
1. LONGBLOB: Large binary data, can store up to 4,294,967,295 bytes.

### Other Datatypes

1. BIT(size): Bit-field type. The default is 1.
1. ENUM('value1', 'value2', ...): Enumeration, a string object that can have one value chosen from a list of values.
1. SET('value1', 'value2', ...): A string object that can have zero or more values, each of which must be chosen from a list of values.
1. JSON: JSON (JavaScript Object Notation) data type, used to store JSON formatted data.

### Spatial Datatypes

1. GEOMETRY: Represents any type of geometry.
1. POINT: A single location in coordinate space.
1. LINESTRING: A series of points in coordinate space, forming a continuous line.
1. POLYGON: A series of points in coordinate space, forming a closed shape.

### RAW and Long RAW Equivalent

MySQL does not have direct equivalents for Oracle's RAW and LONG RAW types, but binary data can be handled using BINARY, VARBINARY, BLOB, and related types.

### Rowid Datatypes

MySQL does not have a direct equivalent of Oracle's ROWID types. Each table with a primary key or unique index can use the key as a unique row identifier.

---

## `MySQL string functions`

Common String Functions in MySQL

### ASCII(str)

- Returns the ASCII code of the leftmost character of the string.
- Example:
  ```sql
  SELECT ASCII('A');  -- Returns 65
  ```

### CHAR(N, ...)

- Returns the character for each integer passed.
- Example:
  ```sql
  SELECT CHAR(65);  -- Returns 'A'
  ```

### CONCAT(string1, string2, ...)

- Concatenates two or more strings.
- Example:
  ```sql
  SELECT CONCAT('Hello', ' World');  -- Returns 'Hello World'
  ```

### INSTR(string, substring)

- Returns the position of the first occurrence of a substring within a string.
- Example:
  ```sql
  SELECT INSTR('Hello World', 'o');  -- Returns 5
  ```

### LENGTH(string)

- Returns the length of the string in bytes.
- Example:
  ```sql
  SELECT LENGTH('Hello World');  -- Returns 11
  ```

### LOWER(string)

- Converts a string to lowercase.
- Example:
  ```sql
  SELECT LOWER('HELLO WORLD');  -- Returns 'hello world'
  ```

### UPPER(string)

- Converts a string to uppercase.
- Example:
  ```sql
  SELECT UPPER('hello world');  -- Returns 'HELLO WORLD'
  ```

### LPAD(string, length, pad_string)

- Pads the left side of a string with a specified character to a certain length.
- Example:
  ```sql
  SELECT LPAD('Hello', 10, '*');  -- Returns '*****Hello'
  ```

### RPAD(string, length, pad_string)

- Pads the right side of a string with a specified character to a certain length.
- Example:
  ```sql
  SELECT RPAD('Hello', 10, '*');  -- Returns 'Hello*****'
  ```

### LTRIM(string, [trim_string])

    - Removes leading spaces or specified characters from the left side of a string.
    - Example:
      ```sql
      SELECT LTRIM('   Hello');  -- Returns 'Hello'
      SELECT LTRIM('***Hello', '*');  -- Returns 'Hello'
      ```

### RTRIM(string, [trim_string])

    - Removes trailing spaces or specified characters from the right side of a string.
    - Example:
      ```sql
      SELECT RTRIM('Hello   ');  -- Returns 'Hello'
      SELECT RTRIM('Hello***', '*');  -- Returns 'Hello'
      ```

### REPLACE(string, from_string, to_string)

    - Replaces occurrences of a substring within a string with another substring.
    - Example:
      ```sql
      SELECT REPLACE('Hello World', 'World', 'MySQL');  -- Returns 'Hello MySQL'
      ```

### SUBSTRING(string, start_position, [length])

    - Extracts a substring from a string starting at a specified position.
    - Example:
      ```sql
      SELECT SUBSTRING('Hello World', 7, 5);  -- Returns 'World'
      ```

### INITCAP(string)

    - Converts the first letter of each word in a string to uppercase and all other letters to lowercase.
    - Example:
      ```sql
      SELECT INITCAP('hello world');  -- Returns 'Hello World'
      ```

### TRIM([LEADING|TRAILING|BOTH] trim_string FROM string)

    - Removes specified characters from the beginning, end, or both sides of a string.
    - Example:
      ```sql
      SELECT TRIM(BOTH '*' FROM '*Hello*');  -- Returns 'Hello'
      ```

### SOUNDEX(string)

    - Returns a phonetic representation of a string.
    - Example:
      ```sql
      SELECT SOUNDEX('Hello');  -- Returns 'H400'
      ```

### CAST(expr AS type)

    - Converts a value of any type into the specified datatype.
    - Example:
      ```sql
      SELECT CAST(123 AS CHAR);  -- Returns '123'
      SELECT CAST('2023-01-01' AS DATE);  -- Returns '2023-01-01'
      ```

### Example Queries

To illustrate how these functions can be used in practice, let's look at some example queries.

#### Example 1: Concatenate and Convert to Uppercase

```sql
SELECT UPPER(CONCAT('Hello', ' World')) AS greeting;
-- Returns 'HELLO WORLD'
```

#### Example 2: Find and Extract Substring

```sql
SELECT SUBSTRING('MySQL Functions', INSTR('MySQL Functions', 'F'), 9) AS substring;
-- Returns 'Functions'
```

#### Example 3: Pad and Trim String

```sql
SELECT TRIM(BOTH '*' FROM LPAD('Hello', 10, '*')) AS padded_trimmed;
-- Returns 'Hello'
```

Note:

1. **IMPORTANT**: string functions do NOT change the data stored in your table, the simply return the altered strings as a result of the query. However, you can then take the returned strings and use them to _alter_ the data in the columns.

---

## `Question 1 - Introduction to MySQL`

Read this introduction to MySQL:

[MySQL Tutorial: A Comprehensive Guide for Beginners](https://www.datacamp.com/tutorial/my-sql-tutorial)

---

## `Question 2 - Downloading and installing MySQL database`

Install MySql Community from here:

[MySQL Community](https://dev.mysql.com/downloads/mysql/)

Download for your operating system.

---

## `Question 3 - Downloading and installing a gui for MySQL database`

For a GUI, you can download MySQL Workbench:

[MySQL Workbench](https://dev.mysql.com/downloads/workbench/)

or

Dbeaver:

[dbeaver](https://dbeaver.io/)

---

## `Question 4 - Creating and using a database`

Create a database called `my_database`. Then start using it. Chain both queries together.

Note:

1. It's not enough to create a database. To use it, you need another command/query to start using it;
1. Chaining queries means writing queries one under the other and ending each query with a ; (semicolon).

Solution:

```sql
create database my_database;
use my_database;
```

---

## `Question 5 - deleting a database`

Delete your `my_database` database.

Note:

1. Before you delete a database, you have to switch to another database. If you have no other database to switch to, switch to to the database `information_schema`. Switching means using the `use` keyword;

Solution:

```sql
use information_schema;
drop database my_database;
```

Note:

1. Henceforth, you are free to create and use any database you like for the following exercises unless otherwise specified;
1. Unless otherwise specified, these exercises will be carried out within a database called `my_database`/

## `Question 5a - create a new database`

Now create another database for your table. The assumption of these exercises, unless otherwise stated is that you will be working with a database called `my_database` but it is up to you. Then switch to the new database.

Solution:

```sql
create database my_database;
use my_database;
```

---

## `Question 6 - Create a new table`

Create a new table called `my_contacts`. The table should have the following columns:

1. ID of datatype int. Give this the attribute of not null and set it as the primary key;
1. To define id as primary key, at the end of the columns define it so: primary key (id)
1. LAST_NAME of datatype varchar with length 30;
1. FIRST_NAME of datatype varchar with length 20;
1. EMAIL of datatype varchar with length 50;
1. BIRTHDAY of datatype date;
1. PROFESSION of datatype varchar with length 50;
1. LOCATION of datatype varchar with length 50;
1. STATUS of datatype varchar with length 20;
1. INTERESTS of datatype varchar with length 100;
1. SEEKING of datatype varchar with length 100.

Notes:

1. While a primary key is not strictly necessary, it is good practice to include a primary key in all tables, perhaps even more than 1;
1. The datatype number is an integer. In this case we are using it as the primary key and therefore it MUST contain a value, In fact we add the qualifier _not null_ to ensure that a value in inputted in this field. Moreover, since we've specified that his field is a primary key, it MUST contain a unique value and therefore it must contain a such a value. _not _ null\* ensures that it contains a value and that value must be unique;
1. The datatype varchar allows a variable-length character string in the database character set. You specify the the database character set when you create your database. The default character set of MySQL is utf8mb4;
1. To find out the character set of your oracle database, use this code:

```sql
SELECT @@character_set_database AS 'Character Set', @@collation_database AS 'Collation';
```

1. varchar allows you to specify column length as either BYTE or CHAR. Default if left out is char (character) and max length is 255;
1. varchar characters are inputted in single quotes;
1. Date is another datatype allowing the input of data. MySQL's default date format is YYYY-MM-DD, so you inpute data data as 90/01/01 for 1st January 1990. More on dates further down;
1. columns are expressed in () and separated by , the comma;
1. Learn to indent with spaces to keep the code readable.

Solution:

```sql
CREATE TABLE my_contacts (
    id INT NOT NULL,
    last_name VARCHAR(30),
    first_name VARCHAR(20),
    email VARCHAR(50),
    birthday DATE,
    profession VARCHAR(50),
    location VARCHAR(50),
    status VARCHAR(20),
    interests VARCHAR(100),
    seeking VARCHAR(100),
    PRIMARY KEY (id)
);

```

---

## `Question 7 - Describe your new table`

Retrieve the form of your my_contacts table.

Notes:

1. Use the keyword _desc_
1. _describe_ works equally well.

Solution:

```sql
desc my_contacts;
```

---

## `Question 8 - Delete your new table`

Delete your new table and create it again.

Notes:

1.  To delete your table use the keyword _drop table `my_table`_

Solution:

```sql
drop table my_contacts;
```

Now recreate the table again exactly as is in Question 6

---

## `Question 9 - Insert a row into your new table`

Insert a record into your 'my_contacts' table.

Notes:

1. The keywords used are `insert into 'your_table' (column_1, column_2, column_n) values (data, data, data_n)`;
1. The values of each column must be written down in the same order as the order of the columns;
1. Since the default date format is YYYY-MM-DD, you must input the date 1990-01-01. You can also insert it as 90-01-01.

Solution:

```sql
insert into my_contacts (id, last_name, first_name, email, birthday, profession, location, status, interests, seeking)
values
(0, 'Borg', 'Alex', 'alex@borg.com', '90-01-01', 'software dev', 'Malta', 'Single', 'computers', 'women for dating');
```

---

## `Question 10 - Insert a row with a null value into your new table`

Insert a record with a null value into your new table.

Notes:

1. To do so, simply use the keyword _null_ as a constraint in place of the data that you would otherwise have inserted.

Solution:

```sql
insert into my_contacts (id, last_name, first_name, email, birthday, profession, location, status, interests, seeking) values (1, 'Cauchi', 'Jason', 'jason@cauchi.com', '1989-11-05', null, 'Malta', null, 'computers', 'women for dating');

```

---

## `Question 11 - View all the records in your table`

View all the records in your table

1. Use the keywords _select_ from your_table;
1. The \* requests the query to retrieve ALL records from your table;
1. \* in Oracle SQL is called "star".

```sql
select * from my_contacts;
```

---

## `Question 12 - Delete all records in your table`

Delete all records from your table.

1. Use the keyword _truncate_ to do so;
1. You also need to use the keyword _table_ to execute this query.

Solution:

```sql
truncate table my_contacts;
```

---

## `Question 13 - Insert 11 more records into your table with one simultaneous query`

Insert 10 records into your table.

Hints:

1. The syntax is exactly the same as for inserting a single row, just separate the rows with a , (comma);
1. Each record should contain its data within brackets ();
1. Each row is inserted as part of an independent query so end each row with a semicolon.

```sql
insert into my_contacts (id, last_name, first_name, email, birthday, profession, location, status, interests, seeking)
values
(0, 'Ayle', 'Alex', 'alex@gmail.com', '1990-01-01', 'lawyer', 'Argentina', 'Single', 'politics', 'women for dating'),
(1, 'Beeble', 'Bob', 'bob@gmail.com', '1988-05-02', 'teacher', 'Belgium', 'Married', 'History', 'international friends'),
(2, 'Carlson', 'Charles', 'charles@gmail.com', '1992-10-03', 'fireman', 'Canada', 'Married', 'Hunting', 'hunting buddies'),
(3, 'Dray', 'David', 'david@gmail.com', '1994-04-15', 'journalist', 'Denmark', 'Single', 'Reading', 'women for dating'),
(4, 'Eliah', 'Elton', 'elton@gmail.com', '1994-05-20', 'engineer', 'England', 'Married', 'Whisky', 'Drinking buddies'),
(5, 'Faulk', 'Francis', 'francis@gmail.com', '1988-06-25', 'software dev', 'France', 'Single', 'computer rpgs', 'women for dating'),
(6, 'Goodson', 'George', 'george@gmail.com', '1990-07-30', 'architect', 'Greece', 'Single', 'art', 'women for dating'),
(7, 'Helt', 'Hazel', 'hazel@gmail.com', '1991-08-01', 'medical doctor', 'Hungary', 'Married', 'gastronomy', 'dining out'),
(8, 'Iveson', 'Ivy', 'ivy@gmail.com', '1989-09-05', 'pilot', 'India', 'Married', 'travel', 'travel groups'),
(9, 'Jicks', 'Jackie', 'jackie@gmail.com', '1993-10-10', 'executive', 'Jordan', 'Single', 'fashion', 'men for dating'),
(10, 'Ktesiphon', 'Kalkos', 'kalkos@gmail.com', '1991-11-15', 'military', 'Greece', 'Married', 'ships', 'promotion'),
(11, 'Larand', 'Lemmuel', 'Lemmuel@gmail.com', '95-12-10', 'digital marketing', 'Scotland', 'Single', 'fishing', 'women for dating');
```

---

## `Question 14 - Delete the current table and recreate it to ensure that all columns require a value`

First delete the current iteration of the `my_contacts` table. Then create it such that every column is required to carry a value. Then populate it with all the records in Question 13, following which describe the table and finally retrieve the records of the new table. Chain all queries together.

Hint:

1. If you don't know how to require a column to have a value, check out the solution to question 6.

Solution:

```sql
drop table my_contacts;

create table my_contacts (
    id int not null,
    last_name varchar(30) not null,
    first_name varchar(20) not null,
    email varchar(50) not null,
    birthday date  not null,
    profession varchar(50) not null,
    location varchar(50) not null,
    status varchar(20) not null,
    interests varchar(100) not null,
    seeking varchar(100)  not null,
    primary key (id)
);

insert into my_contacts (id, last_name, first_name, email, birthday, profession, location, status, interests, seeking)
values
(0, 'Ayle', 'Alex', 'alex@gmail.com', '1990-01-01', 'lawyer', 'Argentina', 'Single', 'politics', 'women for dating'),
(1, 'Beeble', 'Bob', 'bob@gmail.com', '1988-05-02', 'teacher', 'Belgium', 'Married', 'History', 'international friends'),
(2, 'Carlson', 'Charles', 'charles@gmail.com', '1992-10-03', 'fireman', 'Canada', 'Married', 'Hunting', 'hunting buddies'),
(3, 'Dray', 'David', 'david@gmail.com', '1994-04-15', 'journalist', 'Denmark', 'Single', 'Reading', 'women for dating'),
(4, 'Eliah', 'Elton', 'elton@gmail.com', '1994-05-20', 'engineer', 'England', 'Married', 'Whisky', 'Drinking buddies'),
(5, 'Faulk', 'Francis', 'francis@gmail.com', '1988-06-25', 'software dev', 'France', 'Single', 'computer rpgs', 'women for dating'),
(6, 'Goodson', 'George', 'george@gmail.com', '1990-07-30', 'architect', 'Greece', 'Single', 'art', 'women for dating'),
(7, 'Helt', 'Hazel', 'hazel@gmail.com', '1991-08-01', 'medical doctor', 'Hungary', 'Married', 'gastronomy', 'dining out'),
(8, 'Iveson', 'Ivy', 'ivy@gmail.com', '1989-09-05', 'pilot', 'India', 'Married', 'travel', 'travel groups'),
(9, 'Jicks', 'Jackie', 'jackie@gmail.com', '1993-10-10', 'executive', 'Jordan', 'Single', 'fashion', 'men for dating'),
(10, 'Ktesiphon', 'Kalkos', 'kalkos@gmail.com', '1991-11-15', 'military', 'Greece', 'Married', 'ships', 'promotion'),
(11, 'Larand', 'Lemmuel', 'Lemmuel@gmail.com', '95-12-10', 'digital marketing', 'Scotland', 'Single', 'fishing', 'women for dating');

desc my_contacts;

select * from my_contacts;
```

---

## `Question 15 - Define default values for the LOCATION column`

Delete your table and create it anew giving the LOCATION column a default value of 'UK' as a constraint. Then fill in the records in Question 14 with the default location for the following individuals:

(2, Carlson, Charles),
(4, Eliah, Elton),
(5, Faulk, Francis)

Finally run a desc query and retrieve all records.

Notes:

1. Use the _default_ keyword with the default value constraint required in the _create_ _table_ query;
2. When you insert the records, in the values brackets replace the location with _default_.

Hint:

1. If you are defining a field with a default value constraint, it should stand to reason that specifying _not_ _null_ is unnecessary.

Solution:

```sql
create table my_contacts (
    id int not null,
    last_name varchar(30) not null,
    first_name varchar(20) not null,
    email varchar(50) not null,
    birthday date  not null,
    profession varchar(50) not null,
    location varchar(50) default 'UK',
    status varchar(20) not null,
    interests varchar(100) not null,
    seeking varchar(100)  not null,
    primary key (id)
);

insert into my_contacts (id, last_name, first_name, email, birthday, profession, location, status, interests, seeking)
values
(0, 'Ayle', 'Alex', 'alex@gmail.com', '1990-01-01', 'lawyer', 'Argentina', 'Single', 'politics', 'women for dating'),
(1, 'Beeble', 'Bob', 'bob@gmail.com', '1988-05-02', 'teacher', 'Belgium', 'Married', 'History', 'international friends'),
(2, 'Carlson', 'Charles', 'charles@gmail.com', '1992-10-03', 'fireman', default, 'Married', 'Hunting', 'hunting buddies'),
(3, 'Dray', 'David', 'david@gmail.com', '1994-04-15', 'journalist', 'Denmark', 'Single', 'Reading', 'women for dating'),
(4, 'Eliah', 'Elton', 'elton@gmail.com', '1994-05-20', 'engineer', default, 'Married', 'Whisky', 'Drinking buddies'),
(5, 'Faulk', 'Francis', 'francis@gmail.com', '1988-06-25', 'software dev', default, 'Single', 'computer rpgs', 'women for dating'),
(6, 'Goodson', 'George', 'george@gmail.com', '1990-07-30', 'architect', 'Greece', 'Single', 'art', 'women for dating'),
(7, 'Helt', 'Hazel', 'hazel@gmail.com', '1991-08-01', 'medical doctor', 'Hungary', 'Married', 'gastronomy', 'dining out'),
(8, 'Iveson', 'Ivy', 'ivy@gmail.com', '1989-09-05', 'pilot', 'India', 'Married', 'travel', 'travel groups'),
(9, 'Jicks', 'Jackie', 'jackie@gmail.com', '1993-10-10', 'executive', 'Jordan', 'Single', 'fashion', 'men for dating'),
(10, 'Ktesiphon', 'Kalkos', 'kalkos@gmail.com', '1991-11-15', 'military', 'Greece', 'Married', 'ships', 'promotion'),
(11, 'Larand', 'Lemmuel', 'Lemmuel@gmail.com', '95-12-10', 'digital marketing', 'Scotland', 'Single', 'fishing', 'women for dating');
```

---

## `Question 16 - Create a new table with a column with a default value`

Create a new table called `doughnut_list`. The table should have four columns: ID which should be the primary key, DOUGHNUT*NAME (varchar(10)), DOUGHNUT_TYPE (varchar(10)), both of which should be \_not null*. Add a column called DOUGHNUT_COST which should be a float of 3 numbers with 2 behind the decimal point. DOUGHNUT_COST should have a default value of 1.00. Then fill them with these records:

(0, Blooberry, filled, 2.12)  
(1, Cinnamondo, ring, 1.35)  
(2, Rockstar, cruller, 1.35)  
(3, Carameller, cruller, 1.35)  
(4, Appleblush, filled, 1.44)

Notes:

1. to create a float consisting of 3 digits of which 2 come after the decimal point, use dec(3,2)

Hint:

1. If you use a round number with dec(3,2), it will render it as an integer, hence 1.00 => 1.

Solution:

```sql
create table doughnut_list (
    id int not null,
    doughnut_name varchar(10) not null,
    doughnut_type varchar(7) not null,
    doughnut_cost dec(3,2) default 1.35,
    primary key (id)
);

insert into doughnut_list (id, doughnut_name, doughnut_type, doughnut_cost)
values (0, 'Blooberry', 'filled', 2.12),
(1, 'Cinnamondo', 'ring', default),
(2, 'Rockstar', 'cruller', default),
(3, 'Carameller', 'cruller', default),
(4, 'Appleblush', 'filled', 1.43);

desc doughnut_list;

select * from doughnut_list;
```

---

## `Question 17 - Create a new table called easy_drinks`

Create a table called `easy_drinks`. The table should have the following columns: DRINK_NAME, MAIN, AMOUNT1, SECOND, AMOUNT2, DIRECTIONS. Add an ID as primary key. Fill it with the following values:

(0, 'Blackthorn', 'tonic water', 1.5, 'pineapple juice', 1, 'stir with ice, strain into cocktail glass with lemon twist')  
(1, 'Blue Moon', 'soda', 1.5, 'blueberry juice', .75, 'stir with ice, strain into cocktail glass with lemon twist')  
(2, 'Oh My Gosh', 'peach nectar', 1, 'pineapple juice', 1, 'stir with ice, strain into shot glass')  
(3, 'Lime Fizz', 'sprite', 1.5, 'lime juice', .75, 'stir with ice, strain into cocktail glass')  
(4, 'Kiss on the Lips', 'cherry juice', 2, 'apricot nectar', 7, 'serve over ice with straw')  
(5, 'Hot Gold', 'peach nectar', 3, 'orange juice', 6, 'pour hot orange juice in mug and add peach nectar')  
(6, 'Lone Tree', 'soda', 1.5, 'cherry juice', .75, 'stir with ice, strain into cocktail glass')  
(7, 'Greyhound', 'soda', 1.5, 'grapefruit juice', 5, 'serve over ice, st ir well')  
(8, 'Indian Summer', 'apple juice', 2, 'hot tea', 6, 'add juice to mug and top off with hot tea')  
(9, 'Bull Frog', 'iced tea', 1.5, 'lemonade', 5, 'serve over ice with lime slice')  
(10, 'Soda and It', 'soda', 2, 'grape juice', 1, 'shake in cocktail glass, no ice')

Then describe it and finally retrieve all records. Chain all queries into one script.

Hint:

1. Think carefully about the datatypes you need.

Solution:

```sql
create table easy_drinks (
    id int not null,
    drink_name varchar(20) not null,
    main varchar(20) not null,
    amount1 dec(3,1) not null,
    second varchar(20),
    amount2 dec(4,2) default 0.75,
    directions varchar(255),
    primary key (id)
);

insert into easy_drinks (id, drink_name, main, amount1, second, amount2, directions) values (0, 'Blackthorn', 'tonic water', 1.5, 'pineapple juice', 1, 'stir with ice, strain into cocktail glass with lemon twist'),
(1, 'Blue Moon', 'soda', 1.5, 'blueberry juice', 0.75, 'stir with ice, strain into cocktail glass with lemon twist'),
(2, 'Oh My Gosh', 'peach nectar', 1, 'pineapple juice', 1, 'stir with ice, strain into shot glass'),
(3, 'Lime Fizz', 'sprite', 1.5, 'lime juice', 0.75, 'stir with ice, strain into cocktail glass'),
(4, 'Kiss on the Lips', 'cherry juice', 2, 'apricot nectar', 7, 'serve over ice with straw'),
(5, 'Hot Gold', 'peach nectar', 3, 'orange juice', 6, 'pour hot orange juice in mug and add peach nectar'),
(6, 'Lone Tree', 'soda', 1.5, 'cherry juice', 0.75, 'stir with ice, strain into cocktail glass'),
(7, 'Greyhound', 'soda', 1.5, 'grapefruit juice', 5, 'serve over ice, stir well'),
(8, 'Indian Summer', 'apple juice', 2, 'hot tea', 6, 'add juice to mug and top off with hot tea'),
(9, 'Bull Frog', 'iced tea', 1.5, 'lemonade', 5, 'serve over ice with lime slice'),
(10, 'Soda and It', 'soda', 2, 'grape juice', 1, 'shake in cocktail glass, no ice');

desc easy_drinks;

select * from easy_drinks;
```

---

## `Question 18 - SELECT with WHERE`

In question 11, you learned how to select all records. Now retrieve all records from the my_contacts table in the column location of which the data is "UK".

Notes:

1. Use the _where_ keyword;
1. Conditions can be set up using logical operators.

Solution:

```sql
select *
from my_contacts
where location = 'UK';
```

---

## `Question 19 - Add conditions to your select query`

You can select records on the basis of multiple conditions if you use the _and_ keyword. Retrieve all records from `easy_drinks` where amount1 is 1.5 and amount2 is 0.75.

Solution:

```sql
select *
from easy_drinks
where amount1 = 1.5
    and amount2 = 0.75;
```

---

## `Question 20 - Select records with only a few of the columns of the table`

Repeat the previous query (Question 19) but this time retrieve only the data in the DRINK_NAME, MAIN, SECOND and DIRECTIONS columns.

Solution:

```sql
select drink_name, main, second
from easy_drinks
where amount1 = 1.5
    and amount2 = 0.75;
```

---

## `Question 21 - Delete a record from a table`

Delete a record from your `easy_drinks` table using _delete from_ and a condition defined by _where_. Delete the record with the ID of 0. Then delete all records in the table whose AMOUNT1 is equal to or less than 1.5 and AMOUNT2 is equal to or less than 1. Chain all queries into a single script.

Solution:

```sql
delete from easy_drinks
where id = 0;

select * from easy_drinks;

delete from easy_drinks
where amount1 <= 1.5
	and amount2 <= 1;

select * from easy_drinks;
```

---

## `Question 22 - Limiting the number of records retrieved`

You can choose how many records to retrieve even if there are more records that meet your retrieval criteria. Repeat the previous query but this time retrieve only one record of those that meet your retrieval criteria.

Hints:

1. You can use the _limit_ keyword for this.

Solution:

```sql
SELECT drink_name, main, second
FROM easy_drinks
WHERE amount1 = 1.5
    AND amount2 = 0.75
LIMIT 1;

```

N.B. observe how sensible indentation makes the code much easier to read.

---

## `Question 23 - More on time and date`

Create a table called `coffee_reviews` with the following columns: ID (int), LOCATION (varchar(255)), TIME_OF_DAY (timestamp), REVIEW_DATE (date), COFFEE_TYPE (varchar(255)), RATING (number(2)) and COMMENTS (varchar(255)).

Fill it with the following values:  
(0, 'Starbuzz Coffee', 7:43 am, 23/4/24, 'cinnamon glazed', 6, 'too much spice')  
(1, 'Duncan's Donuts', 8:56 am, 25/8/24, 'plain glazed', 5, 'greasy')  
(2, 'Duncan's Donuts', 7:58 pm, 26/4/24, 'jelly', 6, 'stale, but tasty')  
(3, 'Starbuzz Coffee', 10:35 pm, 24/4/24, 'plain glazed', 7, 'warm, but not hot')  
(4, 'Krispy King', 9:39 pm, 24/6/24, 'jelly', 6, 'not enough jelly')  
(5, 'Starbuzz Coffee', 7:48 am, 23/4/24, 'rocky road', 10, 'marshmallows!')  
(6, 'Krispy King', 8:56 am, 25/11/24, 'plain glazed', 8, 'maple syrup glaze')

Notes:

1. To use the timestamp datatype, simply provide the date and time in the YYYY-MM-DD HH:MI:SS format;
1. Similarly, the date datatype should be input in the YYYY-MM-DD format.
1. To escape a single quote such as here: 'Duncan's Donuts', use another one: 'Duncan''s Donuts'.

Solution:

```sql
CREATE TABLE coffee_reviews (
    id INT NOT NULL,
    location VARCHAR(255) NOT NULL,
    time_of_day TIMESTAMP NOT NULL,
    review_date DATE NOT NULL,
    coffee_type VARCHAR(255) NOT NULL,
    rating INT NOT NULL,
    comments VARCHAR(255) NOT NULL,
    PRIMARY KEY (id)
);

INSERT INTO coffee_reviews (id, location, time_of_day, review_date, coffee_type, rating, comments) VALUES
(0, 'Starbuzz Coffee', '2024-04-23 07:43:00', '2024-04-23', 'cinnamon glazed', 6, 'too much spice'),
(1, 'Duncan''s Donuts', '2024-08-25 08:56:00', '2024-08-25', 'plain glazed', 5, 'greasy'),
(2, 'Duncan''s Donuts', '2024-04-26 19:58:00', '2024-04-26', 'jelly', 6, 'stale, but tasty'),
(3, 'Starbuzz Coffee', '2024-04-24 22:35:00', '2024-04-24', 'plain glazed', 7, 'warm, but not hot'),
(4, 'Krispy King', '2024-06-24 21:39:00', '2024-06-24', 'jelly', 6, 'not enough jelly'),
(5, 'Starbuzz Coffee', '2024-04-23 07:48:00', '2024-04-23', 'rocky road', 10, 'marshmallows!'),
(6, 'Krispy King', '2024-11-25 08:56:00', '2024-11-25', 'plain glazed', 8, 'maple syrup glaze');

```

---

## `Question 24 - Text data roping`

MySQL can compare text data with comparison operators in a similar way to numeric values. The comparison operators evaluate everything alphabetically. From the table `easy_drinks`, retrieve all the drinks in the column DRINK_NAME that that begin with the letter L and the letter L ONLY.

Notes:

1. Case matters here. If the first letter in the field is lowercase, but you're searching by uppercase, it will not be retrieved even though the letter may not be the same;
1. The results may not be retrieved alphabetically. There will be exercises further down dealing with this issue.

Solution:

```sql
select * from easy_drinks
where drink_name >= 'L'
    and drink_name <= 'M';

```

---

## `Question 25 -The BETWEEN keyword`

Instead of constructing two clauses linked by _and_, use the keyword _between_ retrieve all drinks whose DRINK_NAME begins 'H' and begins with 'L'. Then write another query to retrieve all records whose AMOUNT1 column is between 1.5 and 2. Chain both queries into one script.

Notes:

1. The first part of this exercise is tricky because though MySQL will retrieve records with data beginning with 'H', it will stop at the letter just before the second letter specified. In other words if the second letter specified is 'Z', the last record it retrieves will be that of data beginning with 'Y'.

Solution:

```sql
select * from easy_drinks
where drink_name between 'H' and 'M';

select * from easy_drinks
where amount1 between 1.5 and 2;
```

---

## `Question 26 - Selecting by OR`

Write a query to retrieve all records from `easy_drinks` that have 'cherry juice' in their MAIN OR SECOND columns. Retrieve only the data in column DRINK_NAME that satisfies these conditions

Solution:

```sql
select drink_name from easy_drinks
where main = 'cherry juice'
    or second = 'cherry juice';
```

---

## `Question 27 - Not equal`

Oracle SQL uses an operator to signify 'not equal' that is different from other computer languages. Write a query to retrieve all records from the `easy_drinks` table whose MAIN column is not equal to 'soda'.

Notes:

1. The 'not equal' operator in Oracle SQL is <>.

Solution:

```sql
select * from easy_drinks
where main <> 'soda';
```

---

## `Question 28 - Retrieving records with null values`

Create a table called `null_values_table`. Give it the following columns: ID, FIRST_NAME, LAST_NAME, HOBBIES. Fill it with some data leaving some fields in the HOBBIES column null. Then write a query to retrieve all those records with a null value in their HOBBIES column.

Notes:

1. The correct way of querying columns that have null values is by using the keywords _is null_.

Solution:

```sql
select * from null_values_table
where hobbies is null;
```

---

## `Question 29 - Wildcards and the LIKE keyword`

The _like_ keyword uses wildcards to search for data on the basis of partially supplied data. In the `my_contacts` table, retrieve all records with data starting with 'women' in the SEEKING column. Then write a query retrieving all records that end in 'oda' in the MAIN column in the `easy_drinks` table. Chain both queries into one script.

Notes:

1. You can use the % (percent) wildcard combined with your supplied data. For example 'women%' retrieves records of all data in the specified column that starts with the word 'women'. Inverting the position would retrieve records of all data in the specified column that ends with the word 'women';
1. The wildcard for a single character is the \_ (underscore) character;

Solution:

```sql
select * from my_contacts
where seeking like 'women%';

select * from easy_drinks
where main like '_oda';
```

---

## `Question 30 - The IN keyword`

Create a table called `black_book`with ID (number) DATE, NAME (varchar2(20)) and RATING (varchar2(20)) columns. Make them all _not_ _null_. ID should be the primary key.

Fill it with the following records:  
(0, 'Alex', 'innovative')  
(1, 'James', 'boring')  
(2, 'Ian', 'fabulous')  
(3, 'Boris', 'ho hum')  
(4, 'Melvin', 'plebeian')  
(5, 'Eric', 'pathetic')  
(6, 'Anthony', 'delightful')  
(7, 'Sammy', 'pretty good')  
(8, 'Ivan', 'dismal')  
(9, 'Vic', 'ridiculous')

Once you have created the table, retrieve all records that have a positive rating, i.e. innovative, fabulous, delightful, pretty good. Chain both queries into one script.

Notes:

1. Use the _in_ keyword and provide the list of matching data in brackets.

Solution:

```sql
create table black_book (
    id int not null primary key,
    date_name varchar(20) not null,
    rating varchar(20) not null
);

insert into black_book (id, date_name, rating)
values
(0, 'Alex', 'innovative'),
(2, 'Ian', 'fabulous'),
(3, 'Boris', 'ho hum'),
(4, 'Melvin', 'plebeian'),
(5, 'Eric', 'pathetic'),
(6, 'Anthony', 'delightful'),
(7, 'Sammy', 'pretty good'),
(8, 'Ivan', 'dismal'),
(9, 'Vic', 'ridiculous');

select *
from black_book
where rating in ('innovative', 'fabulous', 'delightful', 'pretty good');
```

---

## `Question 31 - NOT IN`

Write a query for the table `black_book` retrieving all records that do not have a positive rating.

Hint:

1. This will work similarly to the query in Question 29, but what you're looking for is _not_ _in_ the list of positive ratings.

Solution:

```sql
select *
from black_book
where rating not in ('innovative', 'fabulous', 'delightful', 'pretty good');
```

---

## `Question 32 - More uses of NOT`

Write a query retrieving all data from `easy_drinks` whose DRINK_NAME does NOT begin with a letter falling in the range between 'H' and begins with 'L'. Then write another query to retrieve all records from `my_contacts` whose SEEKING column has data that does not start with "women'. Chain both queries into one script.

Solution:

```sql
select *
from easy_drinks
where drink_name not between 'H' and 'M';

select *
from my_contacts
where seeking not like 'women%';
```

---

## `Question 33 - Similar records`

Create a table called `clown_info` with the following columns: ID (int), NAME (varchar(20)), LAST_SEEN (varchar(255)), APPEARANCE (varchar(255)), ACTIVITIES (varchar(255)). Only ID and NAME should be required. Then fill it with the following values:

(0, 'Elsie', 'Cherry Hill Senior Center', 'F, red hair, green dress, huge feet, balloons', 'little car')  
(1, 'Pickles','Jack Green's party', 'M, orange hair, blue suit, huge feet', 'mime')  
(2, 'Snuggles', 'Ball-Mart', 'F, yellow shirt, baggy red pants, horn', 'umbrella')  
(3, 'Mr. Hobo', 'BG Circus', 'M, cigar, black hair', 'tiny hat,violin')  
(4, 'Clarabelle', 'Belmont Senior Center', 'F, pink hair, huge flower, blue dress', 'yelling, dancing')  
(5, 'Scooter', 'Oakland Hospital', 'M, blue hair, red suit, huge nose', 'balloons')  
(6, 'Zippo', 'Millstone Mall', 'F, orange suit, baggy pants', 'dancing')  
(7, 'Babe,Earl's Autos', 'F, all pink and sparkly', 'balancing', 'little car')  
(8, 'Bonzo', null, 'M, in drag, polka dotted dress', 'singing, dancing')  
(9, 'Sniffles', 'Tracy's', 'M, green and purple suit, pointy nose', null)  
(10, 'Zippo', 'Millstone Mall', 'F, orange suit, baggy pants', 'dancing')  
(11, 'Zippo', 'Millstone Mall', 'F, orange suit, baggy pants', 'dancing, singling')  
(12, 'Zippo', 'Oakland Hospital', 'F, orange suit, baggy pants', 'dancing, singling')  
(13, 'Zippo', 'Tracy's', 'F, orange suit, baggy pants', 'dancing, singling')  
(14, 'Zippo', 'Ball-Mart', 'F, orange suit, baggy pants', 'dancing, singling')  
(15, 'Zippo', 'Millstone Mall', 'F, orange suit, baggy pants', 'dancing, singling')  
(16, 'Zippo', 'Oakland Hospital', 'F, orange suit, baggy pants', 'dancing, singling')

Solution:

```sql
create table clown_info (
    id int not null,
    name varchar(20) not null,
    last_seen varchar(255),
    appearance varchar(255),
    activities varchar(255)
);

insert into clown_info (id, name, last_seen, appearance, activities) values (0, 'Elsie', 'Cherry Hill Senior Center', 'F, red hair, green dress, huge feet, balloons', 'little car'),
(1, 'Pickles','Jack Green''s party', 'M, orange hair, blue suit, huge feet', 'mime'),
(2, 'Snuggles', 'Ball-Mart', 'F, yellow shirt, baggy red pants, horn', 'umbrella'),
(3, 'Mr. Hobo', 'BG Circus', 'M, cigar, black hair', 'tiny hat, violin'),
(4, 'Clarabelle', 'Belmont Senior Center', 'F, pink hair, huge flower, blue dress', 'yelling, dancing'),
(5, 'Scooter', 'Oakland Hospital', 'M, blue hair, red suit, huge nose', 'balloons'),
(6, 'Zippo', 'Millstone Mall', 'F, orange suit, baggy pants', 'dancing'),
(7, 'Babe,Earl''s Autos', 'F, all pink and sparkly', 'balancing', 'little car'),
(8, 'Bonzo', null, 'M, in drag, polka dotted dress', 'singing, dancing'),
(9, 'Sniffles', 'Tracy''s', 'M, green and purple suit, pointy nose', null),
(10, 'Zippo', 'Millstone Mall', 'F, orange suit, baggy pants', 'dancing'),
(11, 'Zippo', 'Millstone Mall', 'F, orange suit, baggy pants', 'dancing, singling'),
(12, 'Zippo', 'Oakland Hospital', 'F, orange suit, baggy pants', 'dancing, singling'),
(13, 'Zippo', 'Tracy''s', 'F, orange suit, baggy pants', 'dancing, singling'),
(14, 'Zippo', 'Ball-Mart', 'F, orange suit, baggy pants', 'dancing, singling'),
(15, 'Zippo', 'Millstone Mall', 'F, orange suit, baggy pants', 'dancing, singling'),
(16, 'Zippo', 'Oakland Hospital', 'F, orange suit, baggy pants', 'dancing, singling');
```

---

## `Question 34 - Retrieve all records with a particular value`

The clown Zippo in the table `clown_info' has multiple records. Retrieve them all.

Solution:

```sql
select *
from clown_info
where name = 'Zippo';
```

Note:

1. The records are retrieved in no order, so with this query, there is no way of knowing the sequence of the records.

---

## `Question 35 - Delete a record`

In the table `clown_info`, there are two records for the clown Zippo that have 'dancing' in the ACTIVITIES column. Delete these records. Then retrieve all the records. Finally reinsert the following values:

(6, 'Zippo', 'Millstone Mall', 'F, orange suit, baggy pants', 'dancing')  
(10, 'Zippo', 'Millstone Mall', 'F, orange suit, baggy pants', 'dancing')

Finally, retrieve all records. Chain all queries into one script.

Notes:

1. use the keyword _delete_ instead of _select_;
1. Observe that in the case of _delete_ it is followed by the keyword _from_ rather than the syntax of _select_;
1. Observe that the last two records are appended to the end of the table, irrespective of the value of the ID column;
1. You can use the other keywords done so far, _where_, _and_, _or_, _between_, _like_ etc. with _delete_;

CAUTION:
`delete from clown_info` deletes all records. In this case it is similar to `truncate table clown_info`.

Solution:

```sql
delete from clown_info
where name = 'Zippo' and activities = 'dancing';

select * from clown_info;

insert into clown_info (id, name, last_seen, appearance, activities)
values (6, 'Zippo', 'Millstone Mall', 'F, orange suit, baggy pants', 'dancing'),
(10, 'Zippo', 'Millstone Mall', 'F, orange suit, baggy pants', 'dancing');

select * from clown_info
```

---

## `Question 36 - Updating a record with DELETE and INSERT`

Create a table called `drink_info` with the following columns: ID (int), DRINK_NAME (varchars(20)), COST (dec(2,1)), CARBS (dec(3,1)) COLOUR (varchar(10)), ICE (char(1)), CALORIES (number). ID should be required, and so should be DRINK_NAME. Insert the following values into it:

(0, 'Blackthorn', 3, 8.4, 'yellow', 'Y', 33)  
(1, 'Blue Moon', 2.5, 3.2, 'blue', 'Y', 12)  
(2, 'Oh My Gosh', 3.5, 8.6, 'orange', 'Y', 35)  
(3, 'Lime Fizz', 2.5, 5.4, 'green','Y', 24)  
(4, 'Kiss on the Lips', 5.5, 42.5, 'purple', 'Y', 171)  
(5, 'Hot Gold', 3.2, 32.1, 'orange', 'N', 135)  
(6, 'Lone Tree', 3.6, 4.2, 'red', 'Y', 17)  
(7, 'Greyhound', 4,14, 'yellow', 'Y', 50)  
(8, 'Indian Summer', 2.8, 7.2, 'brown', 'N', 30)  
(9, 'Bull Frog', 2.6, 21.5, 'tan', 'Y', 80)  
(10, 'Soda and It', 3.8, 4.7, 'red', 'N', 19)

Now with that done, write the following queries:

1. Retrieve all the records of the new table;
1. Change the CALORIES of 'Kiss on the Lips' to 170;
1. Change the 'yellow' values of the COLOUR to 'gold';
1. Make all the drinks that COST 2.50 COST 3.50;
1. Make all the drinks that currently COST 3.50 now COST 4.50;
1. Retrieve all the records of the table as it is now;
1. Delete the table and recreate it with the original values.
1. Chain all queries into one script.

Notes:

1. For this exercise, use the _delete_ keyword and _insert_ to insert the updated records;
2. After you carry out the changes, retrieve all the records.
3. Be very careful when changing the cost. The sequence matters very much unless you want to change all drinks costing both 2.50 and 3.50 to 4.50.

Solution:

```sql
CREATE TABLE drink_info (
    id INT NOT NULL,
    drink_name VARCHAR(20) NOT NULL,
    cost DEC(3,1),
    carbs DEC(4,1),
    colour VARCHAR(10),
    ice CHAR(1),
    calories INT,
    PRIMARY KEY (id)
);

INSERT INTO drink_info (id, drink_name, cost, carbs, colour, ice, calories) VALUES
(0, 'Blackthorn', 3.0, 8.4, 'yellow', 'Y', 33),
(1, 'Blue Moon', 2.5, 3.2, 'blue', 'Y', 12),
(2, 'Oh My Gosh', 3.5, 8.6, 'orange', 'Y', 35),
(3, 'Lime Fizz', 2.5, 5.4, 'green','Y', 24),
(4, 'Kiss on the Lips', 5.5, 42.5, 'purple', 'Y', 171),
(5, 'Hot Gold', 3.2, 32.1, 'orange', 'N', 135),
(6, 'Lone Tree', 3.6, 4.2, 'red', 'Y', 17),
(7, 'Greyhound', 4.0, 14.0, 'yellow', 'Y', 50),
(8, 'Indian Summer', 2.8, 7.2, 'brown', 'N', 30),
(9, 'Bull Frog', 2.6, 21.5, 'tan', 'Y', 80),
(10, 'Soda and It', 3.8, 4.7, 'red', 'N', 19);

-- Update the CALORIES of 'Kiss on the Lips' to 170
DELETE FROM drink_info WHERE drink_name = 'Kiss on the Lips' AND calories = 171;
INSERT INTO drink_info (id, drink_name, cost, carbs, colour, ice, calories) VALUES
(4, 'Kiss on the Lips', 5.5, 42.5, 'purple', 'Y', 170);

-- Change the 'yellow' values of the COLOUR to 'gold'
DELETE FROM drink_info WHERE colour = 'yellow';
INSERT INTO drink_info (id, drink_name, cost, carbs, colour, ice, calories) VALUES
(0, 'Blackthorn', 3.0, 8.4, 'gold', 'Y', 33),
(7, 'Greyhound', 4.0, 14.0, 'gold', 'Y', 50);

-- Make all the drinks that COST 2.50 COST 3.50
DELETE FROM drink_info WHERE cost = 2.5;
INSERT INTO drink_info (id, drink_name, cost, carbs, colour, ice, calories) VALUES
(1, 'Blue Moon', 3.5, 3.2, 'blue', 'Y', 12),
(3, 'Lime Fizz', 3.5, 5.4, 'green', 'Y', 24);

-- Make all the drinks that currently COST 3.50 now COST 4.50
DELETE FROM drink_info WHERE cost = 3.5;
INSERT INTO drink_info (id, drink_name, cost, carbs, colour, ice, calories) VALUES
(1, 'Blue Moon', 4.5, 3.2, 'blue', 'Y', 12),
(3, 'Lime Fizz', 4.5, 5.4, 'green', 'Y', 24),
(2, 'Oh My Gosh', 4.5, 8.6, 'orange', 'Y', 35);

-- Retrieve all the records of the table as it is now
SELECT * FROM drink_info;

-- Delete the table and recreate it with the original values
DROP TABLE drink_info;

CREATE TABLE drink_info (
    id INT NOT NULL,
    drink_name VARCHAR(20) NOT NULL,
    cost DEC(3,1),
    carbs DEC(4,1),
    colour VARCHAR(10),
    ice CHAR(1),
    calories INT,
    PRIMARY KEY (id)
);

INSERT INTO drink_info (id, drink_name, cost, carbs, colour, ice, calories) VALUES
(0, 'Blackthorn', 3.0, 8.4, 'yellow', 'Y', 33),
(1, 'Blue Moon', 2.5, 3.2, 'blue', 'Y', 12),
(2, 'Oh My Gosh', 3.5, 8.6, 'orange', 'Y', 35),
(3, 'Lime Fizz', 2.5, 5.4, 'green','Y', 24),
(4, 'Kiss on the Lips', 5.5, 42.5, 'purple', 'Y', 171),
(5, 'Hot Gold', 3.2, 32.1, 'orange', 'N', 135),
(6, 'Lone Tree', 3.6, 4.2, 'red', 'Y', 17),
(7, 'Greyhound', 4.0, 14.0, 'yellow', 'Y', 50),
(8, 'Indian Summer', 2.8, 7.2, 'brown', 'N', 30),
(9, 'Bull Frog', 2.6, 21.5, 'tan', 'Y', 80),
(10, 'Soda and It', 3.8, 4.7, 'red', 'N', 19);
```

---

## `Question 37 - Updating a column with UPDATE`

Update the table `coffee_reviews` to change all values of 'plain glazed' in the column COFFEE\*TYPE to 'glazed'. Use the keyword _update_ for this. Then retrieve all records from the table. Chain the queries into one script.

Notes:

1. You need to use the keyword _update_;
1. And then select the column using _set_;
1. You can use _where_ and related as per normal.

Solution:

```sql
update coffee_reviews
set coffee_type = 'glazed'
where coffee_type = 'plain glazed';

select * from  coffee_reviews;

```

---

## `Question 38 - Updating multiple columns with UPDATE`

Update the table `my_contacts` with the value 'UK' in the column LOCATION and the value 'single' in the column STATUS with the values 'Malta' and 'married' respectively.

Notes:

1. in the line starting with the keyword _set_ separate multiple columns with a , (comma);

Solution:

```sql
update my_contacts
set location = 'Malta', status = 'married'
where location = 'UK' and status = 'single';
```

---

## `Question 39 - Revisiting Question 36`

In Question 36, you updated the records of table `drink_info` with a cumbersome combination of _delete_ and _insert_. Let's do it again using _set_. The required tasks are:

1 Change the CALORIES of 'Kiss on the Lips' to 170;

1. Change the 'yellow' values of the COLOUR to 'gold';
1. Make all the drinks that COST 2.50 COST 3.50;
1. Make all the drinks that currently COST 3.50 now COST 4.50;
1. Retrieve all the records of the table as it is now;
1. Delete the table and recreate using the original records;
1. Chain all queries into one script.

Solution:

```sql
update drink_info
set calories = 170
where drink_name = 'Kiss on the Lips';

update drink_info
set colour = 'gold'
where colour = 'yellow';

update drink_info
set cost = 4.50
where cost = 3.50;

update drink_info
set cost = 3.50
where cost = 2.50;

select * from drink_info;

drop table drink_info;

create table drink_info (
    id int not null,
    drink_name varchar(20) not null,
    cost dec(2,1),
    carbs dec(3,1),
    colour varchar(10),
    ice char(1),
    calories int,
    primary key (id)
);

insert into drink_info (id, drink_name, cost, carbs, colour, ice, calories) values
(0, 'Blackthorn', 3, 8.4, 'yellow', 'Y', 33),
(1, 'Blue Moon', 2.5, 3.2, 'blue', 'Y', 12),
(2, 'Oh My Gosh', 3.5, 8.6, 'orange', 'Y', 35),
(3, 'Lime Fizz', 2.5, 5.4, 'green','Y', 24),
(4, 'Kiss on the Lips', 5.5, 42.5, 'purple', 'Y', 171),
(5, 'Hot Gold', 3.2, 32.1, 'orange', 'N', 135),
(6, 'Lone Tree', 3.6, 4.2, 'red', 'Y', 17),
(7, 'Greyhound', 4,14, 'yellow', 'Y', 50),
(8, 'Indian Summer', 2.8, 7.2, 'brown', 'N', 30),
(9, 'Bull Frog', 2.6, 21.5, 'tan', 'Y', 80),
(10, 'Soda and It', 3.8, 4.7, 'red', 'N', 19);
```

---

## `Question 40 - Using Case`

In the previous question, using _update_ and _set_ made updating records far more efficient, but there are still inefficiencies and redundancies. Let's use conditionals to carry out the required changes. For your reference, these are the required changes:

1 Change the CALORIES of 'Kiss on the Lips' to 170;

1. Change the 'yellow' values of the COLOUR to 'gold';
1. Make all the drinks that COST 2.50 COST 3.50;
1. Make all the drinks that currently COST 3.50 now COST 4.50;
1. Retrieve all the records of the table as it is now;
1. Delete the table and recreate using the original records;
1. Chain all queries into one script.

Notes:

1. Combine _set_ with _case_, and _when_... _else_;
1. End each conditional clause with _end_ + comma, except the last _end_ which should be ended with a semicomma.
1. You can use _where_ clauses after the _case_ expression;
1. You can use _case_ with _select_, _insert_, _delete_ and _update_.

```sql
UPDATE drink_info
SET calories = CASE
    WHEN drink_name = 'Kiss on the Lips' THEN 170
    ELSE calories
END,
colour = CASE
    WHEN colour = 'yellow' THEN 'gold'
    ELSE colour
END,
cost = CASE
    WHEN cost = 3.50 THEN 4.50
    WHEN cost = 2.50 THEN 3.50
    ELSE cost
END;

select * from drink_info;

drop table drink_info;

create table drink_info (
    id int not null,
    drink_name varchar(20) not null,
    cost dec(2,1),
    carbs dec(3,1),
    colour varchar(10),
    ice char(1),
    calories int,
    primary key (id)
);

insert into drink_info (id, drink_name, cost, carbs, colour, ice, calories) values
(0, 'Blackthorn', 3, 8.4, 'yellow', 'Y', 33),
(1, 'Blue Moon', 2.5, 3.2, 'blue', 'Y', 12),
(2, 'Oh My Gosh', 3.5, 8.6, 'orange', 'Y', 35),
(3, 'Lime Fizz', 2.5, 5.4, 'green','Y', 24),
(4, 'Kiss on the Lips', 5.5, 42.5, 'purple', 'Y', 171),
(5, 'Hot Gold', 3.2, 32.1, 'orange', 'N', 135),
(6, 'Lone Tree', 3.6, 4.2, 'red', 'Y', 17),
(7, 'Greyhound', 4,14, 'yellow', 'Y', 50),
(8, 'Indian Summer', 2.8, 7.2, 'brown', 'N', 30),
(9, 'Bull Frog', 2.6, 21.5, 'tan', 'Y', 80),
(10, 'Soda and It', 3.8, 4.7, 'red', 'N', 19);
```

---
