---
date: 2024-11-02T15:35
tags:
  - "#cybersecurity"
  - "#web-security"
  - "#SQLi"
  - "#injection"
cssclasses:
  - pen-green
  - page-grid
---
#### Error based SQLi
***

Error based SQLi is an in-band injection technique that enables threat actors o exploit error output from the database to manipulate its data.

It manipulates the database into generating an error that informs the actor of the database’s structure

##### Simple Example
***
Original URL:
```
https://example.com/index.php?item=123
```

Add `'` to the parameter
```
https://example.com/index.php?item=123'
```

Results in error:
```
You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ‘‘VALUE’’.
```

From this error message we know:
- Database used is MySQL
- The exact syntax that caused error - single quote
- Syntax error occurred near `VALUE` parameter

##### Advanced Example
****
Consider the same URL, where the attacker knows that database is Oracle 10g

```
https://example.com/index.php?item=123||UTL_INADDR.GET_HOST_NAME( (SELECT user FROM DUAL) )--
```

- the `UTL_INADDR.GET_HOST_NAME()` function which returns the hostname on an Oracle 10g database
- the SQL query `SELECT user FROM DUAL`. The `DUAL` table is a reserved table that exist in any Oracle Database

```
ORA-292257: host DAVID unknown
```

#### Error Based SQLi Prevention
***
- Use prepared statement
- Stored procedures
- principle of least privilege
- allowlist input validation
- Dynamic Application Security Testing (DAST)