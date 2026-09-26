# Room 404

**Room:** Byte Lotus — Room 404
**Difficulty:** Easy

They deployed the app with its `.git` directory still attached, and served it to
anyone who asked.

That is the room. `ffuf` found the path, `.git/refs/heads/main` confirmed it, and the
history gave up the source. Check `.gitignore` before you ship — a version control
directory on a public web root is a self-served source code leak, and the recovery
step afterwards is "rotate everything that was ever committed", not "delete the
folder".

Enumeration and confirmation steps, no flag spoilers:
**[alzeaty1.github.io/writeups/room404](https://alzeaty1.github.io/writeups/room404/)**
