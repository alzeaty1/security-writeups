# Overheard at Breakfast

**Room:** Overheard at Breakfast
**Difficulty:** Easy

**Vulnerability classes:** OSINT, Social Media Analysis, Email Hashing (MD5), Third-Party Profile Enumeration, Base64 Decoding

One screenshot of a leaked conversation was enough to extract an email address. Normalizing it and hashing it to MD5 turned a name into a Gravatar lookup, and the profile behind that hash carried the next clue in base64.

Full write-up (methodology, payloads, no flag spoilers): **[alzeaty1.github.io/writeups/overheard-at-breakfast](https://alzeaty1.github.io/writeups/overheard-at-breakfast/)**
