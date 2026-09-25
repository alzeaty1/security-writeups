# Beach Bar

**Room:** Beach Bar
**Difficulty:** Easy

**Vulnerability classes:** Unsafe Deserialization (PyYAML RCE), Default Credentials, Credential Exposure in Process Arguments, Password Reuse, Privilege Escalation

An unsafe `yaml.load()` on attacker-controlled input gave RCE, and a root daemon passing its password as a command-line argument turned that into a full privesc chain. The two flaws are independent; the second one is what made the first one worth anything.

Full write-up (methodology, payloads, no flag spoilers): **[alzeaty1.github.io/writeups/beach-bar](https://alzeaty1.github.io/writeups/beach-bar/)**

## In this folder

- `beachbar_rce.py` - PyYAML deserialization RCE payload generator.

Key values are left blank on purpose in the teaching versions. Work the room first.
