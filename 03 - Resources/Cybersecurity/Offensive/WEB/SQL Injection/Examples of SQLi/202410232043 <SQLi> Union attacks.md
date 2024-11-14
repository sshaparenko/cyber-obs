---
date: 2024-10-23T20:43
tags:
  - "#cybersecurity"
  - "#offensive"
  - "#SQLi"
cssclasses:
  - pen-green
  - page-grid
---
When an application is vulnerable to SQL injection and the results of the query are returned within the application’s responses, you can use the `UNION` keyword to retrieve data from other tables within the database.

This is commonly known as SQLi UNION attack

The `UNION` keyword enables you to execute one or more additional `SELECT` queries and append the results to the original query. For example:

```sql
SELECT a, b FROM table1 UNION SELECT c, d FROM table2
```

This SQL query returns a single set with two columns, containing values from columns `a` and `b` in `table1` and columns `c` and `d` from `table2`

For a `UNION` query to work, two key requirements must be met:

- **Individual queries must return the same number of columns**
- **The data types in each column must be compatible between the individual queries**

To carry out the SQLi UNION attack, make sure that your attack meets these two requirements. This normally involves finding out:

- **How many columns are being returned from the original query**
- **Which columns returned from the original query are of a suitable data type to hold the results from the injected query**

#### Determining the number of columns required
***
First method involves injecting a series of `ORDER BY` clauses and incrementing the specified column index until an error occurs.

For example if the injection point is a quoted string within the `WHERE` clause of the original query, you would submit

```
' ORDER BY 1--
' ORDER BY 2--
' ORDER BY 3--
```

The second method involves submitting a series of `UNION SELECT`

```
' UNION SELECT NULL--
' UNION SELECT NULL, NULL--
' UNION SELECT NULL NULL, NULL--
```

### On Oracle every SELECT must use the FROM keyword

There is a build-in table on Oracle called dual which can be used for this purpose. So the injected queries on Oracle would look like:
```
' UNION SELECT NULL FROM DUAL--
```

#### Finding columns with a useful data type
***
`UNION` attack enables you to retrive the results from an injected query. 

The interesting data that you want to retrieve is normally in form of a string 

After you determine the number of columns, you can probe column to test whether it can hold string data

```
' UNION SELECT 'a',NULL,NULL,NULL,NUL--
' UNION SELECT NULL,'a',NULL,NULL,NUL--
' UNION SELECT NULL,NULL,'a',NULL,NUL--
```

The error massage could be `Conversion failed when converting the varchar value 'a' to data type int.`

#### Retrieving interesting data 
***

In case if we know, that database has a table called `users` that has two columns `username` and `password`, we can craft a query to retrieve all data from `users` table

```
' UNION SELECT username, password FROM users--
```

#### Retrieving multiple values within a single column