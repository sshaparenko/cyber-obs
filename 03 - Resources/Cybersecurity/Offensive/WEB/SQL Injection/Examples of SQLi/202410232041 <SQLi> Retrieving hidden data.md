---
date: 2024-10-23T20:41
tags:
  - "#cybersecurity"
  - "#SQLi"
  - "#offensive"
cssclasses:
  - pen-green
  - page-grid
---
Imagine a shopping application that displays products by different categories

When the user clicks on the `Gifts` category their browser request URL:

`https://shop.com/products?category=Gifts`

This causes the application to make a SQL query to retrieve details of the relevant product from the database

```sql
SELECT * FROM products WHERE category = 'Gifts' AND released = 1
```

The restriction `released = 1` is being used to hide products that are not released. We could assume for unreleased products `released` will be `0`

The application doesn’t have any defenses against SQL injection attack. This means an attacker can construct the following attack:

`https://shop.com/products?category=Gifts'--`

This `--` will comment the `released = 1` and SQL query will look like this:

```sql
SELECT * FROM products WHERE category = 'Gifts'--released = 1
```

