---
date: 2024-11-09T16:44
tags:
  - "#cybersecurity"
  - "#web-security"
cssclasses:
  - pen-green
  - page-grid
---
**HTTP session implementation** managed by:

**Web-Server:**
- stored in tmp-files memory
- without [[202411091647 Session Locking|locking]]

**Framework:**
- stored in tmp-files, databases, memory
- with/without [[202411091647 Session Locking|locking]]

**Custom code:**
- stored in tmp-files, databases (mostly), memory
- with/without [[202411091647 Session Locking|locking]]

**HTTP Session** can be represented by:
- ID/token as part of GET
- ID/token in cookie
- ID/token as part of POST