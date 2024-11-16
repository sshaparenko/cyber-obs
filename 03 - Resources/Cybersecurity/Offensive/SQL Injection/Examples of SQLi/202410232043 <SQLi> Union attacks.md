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