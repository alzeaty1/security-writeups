# SQL Injection

**Room:** SQL Injection (THM practical)
**Difficulty:** Easy

Four levels that look like four different applications are one endpoint and one bug:
a query string concatenated into a statement. What changes between the levels is only
how much the app is willing to tell you.

- **UNION** — when the app returns your data back, ask it to return a row you built.
- **`OR 1=1;--`** — comment out the rest of the query and make the condition
  unconditional. Authentication stops being authentication.
- **Boolean blind** — the response is a flat yes/no, so extract a value one character
  at a time: `LIKE 'prefix%'` means "is the next character this one?", and you get 30
  requests per correct guess.
- **Time-based blind** — when even the boolean is gone, the only channel left is
  latency. `SLEEP` runs or it does not, and you read the answer off a stopwatch.

The scripts in this folder implement the two slow oracles, deliberately: linear
charset scan, no concurrency, no binary search. Fast versions exist and they change
the character of the request pattern. These are for understanding the oracle, not for
beating a clock.

**In this folder**
- `boolean_blind_enum.py` — the `LIKE 'prefix%'` oracle, reading `error: true/false`.
- `time_based_enum.py` — the `SLEEP` oracle, preferring the server's own leaked query
  time over wall-clock measurement, with a fallback.

Both read a `BASE_URL` you have to set yourself. I am not shipping a working scanner
against a THM instance; the payload templates and the oracle logic are the lesson.

Methodology, all four levels, no flag spoilers:
**[alzeaty1.github.io/writeups/sqli](https://alzeaty1.github.io/writeups/sqli/)**
