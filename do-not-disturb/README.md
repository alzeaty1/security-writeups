# Do Not Disturb

**Room:** Do Not Disturb
**Difficulty:** Medium

**Vulnerability classes:** NoSQL Injection, Server-Side Template Injection, Remote Code Execution, Privilege Escalation

A `{"$ne": ""}` payload bypassed the MongoDB-backed login, EJS template injection gave RCE, and the shell that came back had a Node.js inspector bound to loopback. Two privilege escalations followed: a service account, then a `debugfs` read of the raw block device.

Full write-up (methodology, payloads, no flag spoilers): **[alzeaty1.github.io/writeups/do-not-disturb](https://alzeaty1.github.io/writeups/do-not-disturb/)**
