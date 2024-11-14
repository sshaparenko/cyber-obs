---
date: 2024-11-02T15:28
tags:
  - "#cybersecurity"
  - "#web-security"
  - "#SQLi"
  - "#injection"
cssclasses:
  - pen-green
  - page-grid
---
Example of a piggy backed query

```sql
SELECT pass FROM userTable WHERE user_id = ' + userid + '
```

`userid = 1 AND Passwoed = 0; drop userTable;--`

```sql
SELECT pass FROM userTable WHERE user_id = 1 1 AND Passwoed = 0; drop userTable; --'
```

