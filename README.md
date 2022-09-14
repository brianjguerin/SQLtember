# SQLtember
(surely boring) Adventures in Learning SQL

It's everybody's favorite time of the year, SQLtember!  This is my running blog of learning SQL.  I hope to update it daily during the month.  I recently completed (well, just about finished now) the Google for Data Analytics track on Coursera.  That course gave a brief introduction to SQL and exposure to Google's Big Query platform but more practice is needed to gain a good grasp. 

## Resources
* [Sam's Teach Yourself SQL in 10 Minutes by Ben Forta](https://www.amazon.com/SQL-Minutes-Sams-Teach-Yourself/dp/0672336073)
* (maybe) [SQL for Data Science course on Coursera](https://www.coursera.org/learn/sql-for-data-science)
* [w3 Schools SQL Tutorial](https://www.w3schools.com/sql/)
* [SQL Tutorial](https://www.sqltutorial.org/)
* [SQL-In-depth-guide_-SQL-best-practices.pdf](https://github.com/brianjguerin/SQLtember/files/9474047/SQL-In-depth-guide_-SQL-best-practices.pdf)
* [Intermediate-Guide-to-SQL.pdf](https://github.com/brianjguerin/SQLtember/files/9474045/Intermediate-Guide-to-SQL.pdf)
* [Setting Up a DBMS](https://cierra-andaur.medium.com/sams-teach-yourself-sql-in-10-minutes-a-day-setting-up-for-success-76dd346e5dd)
* [Why You Need a Database by Derek Sivers](https://sive.rs/dbt)



### September 1

Completed
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 1: Understanding SQL 

Terms
* SQL - Structured Query Language, the language for querying databases
* Database - A container to store organized data
* DBMS - Database Management System, the software used to create and manage databases
* Table - A structured list of data of a specific type
* Schema - Information about database and table layout and properties
* Column - A single field in a table
* Datatype - A type of allowed data
* Row - A record in a table
* Primary key - A column whose value uniquely identifies every row in a table
  * No two rows can have the same primary key value
  * Every row must have a value in the primary key column (no nulls)
  * Values in primary key columns should never be modified or updated
  * Primary key values should never be reused

Notes
* Some DBMS have SQL extensions that add statements to standard SQL but all major DBMS support ANSI SQL
* There are many choices for a DBMS, cloud-based solutions from Google, Amazon, Microsoft, Oracle, and IBM as well as traditional desktop options such as MySQL, PostgreSQL, SQLite, and Microsoft SQL Server

Up Next
* Setup desktop DBMS
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 2: Retrieving Data
* SQL Tutorial - Section 1: Introduction to SQL

### September 2

Completed
* Downloaded MySQL and MySQL Workbench
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 2: Retrieving Data
* SQL Tutorial - Section 1: Introduction to SQL

Terms
* Keyword - Reserved word that is part of the SQL language.  Be careful not to name tables or columns using a keyword.  Here is a [list of SQL reserved words](https://en.wikipedia.org/wiki/SQL_reserved_words)

SQL
* SELECT - Used to select which rows to return in a query
* FROM - Specifies which database / table the query should pull from
* DISTINCT - Returns only unique values of specified column, when more than one column is specified it will return the unqiue records / rows, not just the unique values in each column
* LIMIT - Tells DBMS to return no more than specified number of rows
* OFFSET - Used with LIMIT, specifies which row to start from

Notes
* SQL commands are terminated by a semicolon (;)
* There are three ways to comment in SQL
  * -- is typically used for single line comments
  * Octothorpe (#) is also used for single line comments but less common
  * /* */ is used for multi-line comments
* It is common practice to use uppercase for SQL keywords and lowercase for column and table names
* SQL ignores extra white space
* When using SELECT multiple column names are separated by commas
* Using a wildcard (*) in a SELECT statement returns all columns
* Rather than using OFFSET, you can use this syntax: LIMIT x,y where x is the offset and y is the limit
  
Up Next
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 3: Sorting Retrieved Data
* I will skip the other tutorials for now as they seem redundant

### September 3

Completed
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 3: Sorting Retrieved Data

Terms
* Clause - SQL statements are made up of clauses, some required and some optional.  A clause usually consists of a keyword and data

SQL
* ORDER BY - Sorts output based on one or more columns
* DESC - Specifies sort order descending (ascending is default).  Comes after the column argument in ORDER BY clause
* ASC - Specifies sort order ascending.  Not necessary as ascending is the default

Notes
* You should not rely on the order of the returned results if ordering was not explicity specified
* If using ORDER BY it must be the last clause in your SELECT statement
* It is possible to sort output by a column that was not selected for display
* When sorting by multiple columns use ORDER BY and separate columns with a comma.  Order matters and the output will be sorted by the first specified column, then by the next.  The second argument only comes into play if there are duplicate values in the first specified column
* Position can be used for sorting by specifying the column numbers.  The column numbers refer to their position in the SELECT statement.  ORDER BY 2, 3 would be selecting the second then third columns specified in the SELECT statement.  This can be dangerous if you re-order or modify the SELECT statement later on
* DESC will only apply to the column directly preceding it. If sorting DESC on multiple columns, it must be added after each

Up Next
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 4: Filtering Data

### September 4

Completed
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 4: Filtering Data

Terms
* NULL - No value as opposed to 0, empty string (''), or just spaces

SQL
* WHERE - Clause that filters data by specifying search criteria. Comes right after the table name / FROM clause
* BETWEEN - Used in the WHERE clause to retrieve a range of values. Takes two values separated by AND as arguments. Return range includes the start and end of range
* AND - Used to separate values of range for BETWEEN operator
* IS NULL - Clause used in WHERE clause to check for columns with NULL values

WHERE Clause Operators

|Operator|Description|
|---|---|
|=|Equality|
|<>|Nonequality|
|!=|Nonequality|
|<|Less than|
|<=|Less than or equal to|
|!<|Not less than|
|>|Greater than|
|>=|Greater than or equal to|
|!>|Not greater than|
|BETWEEN|Between two specified values|
|IS NULL|Is a NULL value|

Notes
* Data can also be filtered by the tool that retrieves data from the DBMS rather than the DBMS itself. This is inefficient and can dramatically impact application performance
* When using ORDER BY and WHERE, make sure ORDER BY comes after WHERE
* Rows with NULL in the filter column are not returned when filtering for matches or nonmatches

Up Next
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 5: Advanced Data Filtering

### September 5

Completed
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 5: Advanced Data Filtering

Terms
* Operator - A special keyword used to join or change clauses within a WHERE clause

SQL
* AND - Keyword used to append conditions to WHERE clause. Specifies that only rows matching all conditions should be retrieved
* OR - Keyword used in WHERE clause to specify that any rows matching either of the specified conditions should be retrieved
* IN - Keyword used in WHERE clause to specify a list of values to be matched using an OR comparison
* NOT - Keyword used in WHERE clause to negate a condition

Notes
* When using AND all conditions must be true to retrieve a row.  When using OR rows are retrieved that meet at least one of the conditions
* SQL evaluates AND operators before OR operators.  To get around this, you can group operators using paretheses.  Whenever using both AND and OR / IN operators in a WHERE clause, use parnetheses to explicitly group operators
* IN accomplishes the same thing as OR.  Advantages to IN are as follows:
  * Syntax is cleaner and easier to read
  * Order of evaluation is easier to manage
  * IN operators execute more quickly than OR
  * IN operator can contain another select statement, enabling more dynamic WHERE clauses
* NOT accomplishes same thing as <>.  The advantage of NOT comes in larger queries, especially when used in conjunction with IN and a list of values

Up Next
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 6: Using Wildcard Filtering

### September 6

Completed
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 6: Using Wildcard Filtering

Terms
* Wildcards - Special characters used to match parts of a value
* Search pattern - Search condition made up of literal text, wildcard characters, or any combination of the two
* Predicate - Similar to operator, LIKE is a predicate

SQL
* Wildcards
  * Percent sign (%) - Match any number of occurences of any character
  * Underscore _ - Like percent, but matches only one character
  * Brackets [] - Specifies a set of characters in a certain order. Not supported by most DBMS

Notes
* Wildcard filtering can only be used with text / strings
* Searches may be case sensitive depending on DBMS
* Wildcards can be used anywhere in search pattern and multiple wildcards can be used
* % sign matches one or more characters but can also match zero characters
* Beware trailing spaces.  These can throw off wildcard searches
* % searches will not match NULL values
* The caret (^) character negates bracket wildcards
* Tips for Using Wildcards
  * Don't overuse wildcards
  * Try not to use them at the beginning of the search pattern unless absolutely necessary.  These are the slowest to process
  * Pay careful attention to the placement of the symbols

Up Next
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 7: Creating Calculated Fields

### September 7

Completed
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 7: Creating Calculated Fields

Terms
* Field - Essentially same as database column but typically used to refer to a calculated field
* Concatenate - Joining values together (by appending them to each other) to form a single long value

SQL
* Concatenation - + or || in most DBMS, Concat() with values separate by commas in MySQL
* RTRIM() - Trims all space from the right of a value
* LTRIM() - Trims all space from the left of a value
* TRIM() - Trims all space from both sides of a value
* AS - Used in the SELECT statement to create an alias for a calculated field

Notes
* Field calculations (conversions, reformatings, etc.) can be performed in the client application but as a rule it is quicker to perform these operations on the database side
* Result of concatenation is an unnamed column which cannot be used by the client application since there is no way to refer to it
* Aliases, also known as derived columns, allow client applciations to refer to calculated fields
* Alias names should be either single words or complete strings.  Single word aliases are much safer as multiword names may create problems for client applications
* You can test functions and calculations by omitting the FROM clause in the SELECT statement.  Only the result of your calculation will be returned
* SQL supports the following mathematical operators for calculated fields:

|Operator|Description|
|---|---|
|+|Addition|
|-|Subtraction|
|*|Multiplication|
|/|Division|

Up Next
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 8: Using Data Manipulation Functions

### September 8

Completed
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 8: Using Data Manipulation Functions

Terms
* Functions - Operations that are usually performed on data to facilitate conversion and manipulation
* Portable - Code that is written so that it will run on multiple different systems

SQL
* Commonly Used Text Manipulation Functions

|Function|Description|
|---|---|
|LEFT()|Returns characters from left of string|
|LENGTH()|Returns the length of a string|
|LOWER()|Converts string to lowercase|
|LTRIM()|Trims white space from left of string|
|RIGHT()|Returns characters from right of string|
|RTRIM()|Trims white space from right of string|
|SUBSTR() or SUBSTRING()|Extracts part of a string|
|SOUNDEX|Returns a string's SOUNDEX value|
|UPPER()|Converts string to uppercase|

* Commonly Used Numeric Manipulation Functions

|Functions|Description|
|---|---|
|ABS()|Returns a number's absolute value|
|COS()|Returns the trigonometric cosine of a specified angle|
|EXP()|Returns the exponential value of a specific number|
|PI()|Returns the value of Pi|
|SIN()|Returns the trigonometric sine of a specified angle|
|SQRT()|Returns the square root of a specified number|
|TAN()|Returns the trigonometric tangent of a specified angle|

Notes
* Functions tend to be very DBMS specific.  Very few are supported identically by all major DBMSs
* When using functions make sure to comment your code so you will know which SQL implementation you were writing to
* SOUNDEX uses alphanumeric pattern describing the phonetic representation of that text.  Very cool concept and can come in handy when searching for names that are misspelled or mistyped
* Date manipulation functions are among the least portable between DBMSs

Up Next
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 9: Summarizing Data

### September 9

Completed
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 9: Summarizing Data

Terms
* Aggregate Functions - Functions that operate on a set of rows to calculate and return a single value

SQL
* SQL Aggregate Functions

|Function|Description|
|---|---|
|AVG()|Returns a column's average value|
|COUNT()|Returns the number of rows in a column|
|MAX()|Retruns a column's highest value|
|MIN()|Retruns a column's lowest value|
|SUM()|Returns the sum of a column's values|

Notes
* Columns containing NULL values are ignored by AVERAGE, MAX, MIN, SUM functions
* Columns containing NULL values are ignored by COUNT function unless using *
* Some DBMSs allow MAX to be used on textual columns.  MAX would return the row that would be last if the data were sorted by that column.  MIN would return the first row
* All aggregate functions can be used to perform calculations on multiple columns using standard mathematical oeprators (SUM(quantity * price)) will return sum of expanded prices)
* SUM and AVERAGE can be used with DISTINCT to count each unique value only once
* Using DISTINCT with MIN and MAX serves no purpose as the value will not change
* When using DISTINCT with COUNT a column must be specified, not a calculation or expression, and never with *
* Depending on the DBMS TOP and TOP PERCENT can be used to perform calculations on a subset or queries
* SELECT statements can contain multiple aggregate functions

Up Next
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 10: Grouping Data

### September 10

Completed
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 10: Grouping Data

SQL
* GROUP BY - Groups rows that have the same values into summary rows.  Often used with aggregate functions
* HAVING - Similar to WHERE but used for filtering groups

Terms

Notes
* GROUP BY clauses can contain as many columns as you want, allowing for nesting of groups
* When you have nested GROUP BY statements, data is summarized at the last specified group.  All the statemetns are evaluated together, not by individual column
* Most SQL implementations do not allow GROUP BY columns with variable-length datatypes (such as text or memo fields)
* Every column listed in GROUP BY must be a retrieved column of a valid expression (but not an aggregate function)
* Aside from aggregate calculations, every column in your SELECT statement must be present in the GROUP BY clause
* If the grouping column contains a row with a NULL value, NULL will be returned as a group and all NULLs will be grouped together
* GROUP BY clause must come after any WHERE clause and before any ORDER by clause
* ORDER BY Versus GROUP BY:

|ORDER BY|GROUP BY|
|---|---|
|Sorts generated output.|Groups rows. The output might not be in group order, however.|
|Any columns (even columns not selected) may be used|Only selected columns or expressions columns may be used, and every selected column expression must be used.|
|Never required.|Required if using columns (or expressions) with aggregate functions.|

* As a rule you should always specify and ORDER BY clause any time you use a GROUP BY clause
* SELECT Clauses and Their Sequence:

|Clause|Description|Required|
|---|---|---|
|SELECT|Columns or expressions to be returned|Yes|
|FROM|Table to retrieve data from|Only if selecting data from a table|
|WHERE|Row-level filtering|No|
|GROUP BY|Group specification|Only if calculating aggregates by group|
|HAVING|Group-level filtering|No|
|ORDER BY|Output sort order|No|

Up Next
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 11: Working with Subqueries

### September 11

Completed
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 11: Working with Subqueries

SQL

Terms
* Query - Any SQL statement, usually used to refer to SELECT statements

Notes
* A subquery is a query nested within another query.  The inner-most query will be executed first
* SELECT subqueries can only return one column
* Subqueries can be used as calculated fields
* When comparing information from different tables it is prudent to use the Table.column syntax so SQL knows exactly which column you are requesting
* Subqueries may not be the most efficient way to retrieve data.  Often JOINs can work better

Up Next
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 12: Joining Tables

### September 12

Completed
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 12: Joining Tables

SQL
* INNER JOIN - Uses ON and a join condition to join two tables

Terms
* Scale - Able to handle an increasing load without failing.  Well-designed databases or applications are said to scale well
* Cartesian Product - The results returned by a table relationship without a join condition. The number of rows retrieved will be the number of rows in the first table mulitiplied by the number of rows in the second table
* Cross Join - Another term for Cartesian product
* Equijoin - Join based on testing of equality between two tables

Notes
* Relational databases exist so that information is not repetaed.  A table exists for each type of data.  These tables are related to each other through common values
* Information is not repeated so space is not wasted, only one record needs to be updated if something changes, data is more consistent since there is no repeat entry of the same information
* Joins do not exist in the database and persist only for the duration of the query execution
* Make sure all joins have WHERE clauses, otherwise you will get far more data than you want
* There is no limit to the number of tables that may be joined in a SELECT statement

Up Next
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 13: Creating Advanced Joins

### September 13

Completed
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 13: Creating Advanced Joins

SQL
* LEFT OUTER JOIN - Joins all rows from left table with rows from right table even if there is no corresponding row in right table
* RIGHT OUTER JOIN - Joins all rows from right table with rows from left table even if there is no corresponding row in left table
* FULL OUTER JOIN - Joins all rows from both tables and relates all those that can be related, not available in MySQL

Terms
* Self Joins - A join where the a table is joined with iteself
* Natural Joins - A join where only one occurence of each column shows up in the resulting table

Notes
* Most often you will want to use INNER JOIN
* Always provide a join condition or you will end up with a Cartesian product
* Multiple tables and join types can be combined but make sure to test them individually first

Up Next
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 14: Combining Queries

### September 14

Completed
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 14: Combining Queries

SQL
* UNION - Used to combine multiple SELECT statements, outputs the results into a single result set

Terms
* Unions (Compound Queries) - Multiple queries that return a single result set

Notes
* For the most part, combining two quieries to the same table accomplishes the same thing as a single query with multiple WHERE clause conditions
* A UNION must be composed to two or more SELECT statements, each separated by the keyword UNION
* Each query in a UNION must contain the same columns, expressions, or aggregate functions
* UNION column datatypes must be compatible
* If SELECT statements that are combined with a UNION have different column names, the name in the first SELECT will be used
* UNION automatically removes any duplicate rows from the result set
* UNION ALL returns all results, including duplicate rows. There is no way to do this with a WHERE clause
* When using UNION you may use only one ORDER BY clause and it must come after the final SELECT statement

Up Next
* Sam's Teach Yourself SQL in 10 Minutes - Chapter 15: Inserting Data
