# Room 404

**Room:** Byte Lotus - Room 404
**Difficulty:** Easy

**Vulnerability classes:** Information Disclosure, Exposed Version Control Directory (.git), Directory Enumeration with ffuf

A Python/Werkzeug app on port 8080 shipped its `.git` directory to anyone who asked. `ffuf` found it; `.git/refs/heads/main` confirmed it; the history gave up the source.

Full write-up (methodology, payloads, no flag spoilers): **[alzeaty1.github.io/writeups/room-404](https://alzeaty1.github.io/writeups/room-404/)**
