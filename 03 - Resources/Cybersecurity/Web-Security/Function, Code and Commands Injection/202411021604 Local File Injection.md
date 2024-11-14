---
date: 2024-11-02T16:04
tags:
  - "#cybersecurity"
  - "#web-security"
  - "#injection"
cssclasses:
  - pen-green
  - page-grid
---
In case if we have the next php code:
```php
<?php include("includes/" . $_GET['file'] . "html")
```

If we pass file via a parameter like `?file=../../../etc/passwd%00` by specifying `%00` we will ignore the `.html` extension that was added in code via concatenation 