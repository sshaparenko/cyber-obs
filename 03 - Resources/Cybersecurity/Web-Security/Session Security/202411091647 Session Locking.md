---
date: 2024-11-09T16:47
tags:
  - "#cybersecurity"
  - "#web-security"
cssclasses:
  - pen-green
  - page-grid
---
**Session locking** means that [[Session Identifier SID|SID]] is locked to another session attribute so to prove it’s authority

`For example, if an attacker somehow obtained the session, he could probably ride the session. But it case, it this session was locked with browser version Mozilla v1, if attacker will try to use this session on Google Chrome, it will be treated as an attack This is because the session is unique for each browser`

**Strong** [[Session Identifier SID|SID]]:
- valid for ONE single session
- time limited
- purely random

```
Which attricbute and how can be obtained, tracked and stored?
- Application Server (A)
- Framework (F)
- Custom Code (C)
```

Session Possible attributes:
- Identifier (AFC) - headers
- Browser (FC) - headers
- IP (FC) - protocol
- Current User (FC)
- Device (C) - JS
- Screen resolution (C) - JS
