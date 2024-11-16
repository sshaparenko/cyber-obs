---
date: 2024-10-23T20:42
tags:
  - "#cybersecurity"
  - "#SQLi"
  - "#offensive"
cssclasses:
  - pen-green
  - page-grid
---
Imagine an application that lets users log in with a username and password. If a user submits the username `wiener` and password `bluecheese`, the application checks the credentials by performing the following SQL query:

```sql
SELECT * FROM users WHERE username = 'wiener' AND password = 'bluecheese'
```

In this case, an attacker can log in as any user without the need of the password

```sql
SELECT * FROM users WHERE username = 'administrator'--'AND password =
```