# SQL Injection

**Room:** SQL Injection (THM practical)
**Difficulty:** Easy

**Vulnerability classes:** SQL Injection, UNION-based, Authentication Bypass, Boolean Blind, Time-based Blind

Four training levels that look like four different applications are one endpoint with one bug. UNION to read the table, `OR 1=1;--` to skip authentication entirely, boolean blind to enumerate a value one character at a time, and a timing oracle for when the boolean route gets slow.

Full write-up (methodology, payloads, no flag spoilers): **[alzeaty1.github.io/writeups/sqli](https://alzeaty1.github.io/writeups/sqli/)**

## In this folder

- `boolean_blind_enum.py` - boolean blind, single character.
- `time_based_enum.py` - time-based blind against the timing oracle.

Key values are left blank on purpose in the teaching versions. Work the room first.
