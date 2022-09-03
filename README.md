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
* Some DBMS have SQL extensions that add statements to standard SQL but all major DBMS suppor ANSI SQL
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

SQL Statements
* SELECT - used to select which rows to return in a query
* FROM - specifies which database / table the query should pull from
* DISTINCT - returns only unique values of specified column, when more than one column is specified it will return the unqiue records / rows, not just the unique values in each column
* LIMIT - tells DBMS to return no more than specified number of rows
* OFFSET - used with LIMIT, specifies which row to start from

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
