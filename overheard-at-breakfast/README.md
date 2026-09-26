# Overheard at Breakfast

**Room:** Overheard at Breakfast
**Difficulty:** Easy

One leaked screenshot of a conversation was the whole entry point. From it: an email
address, which is a person's name in a different encoding.

Normalize the address, MD5 it, and Gravatar's public API will tell you whether a
profile exists for that hash without you ever sending the address anywhere. That
profile led to the next clue, which was base64.

No scanning, no exploit, no server to attack. Every step was a public API and a hash
function, and the whole room fell apart once I stopped thinking of the email address
as an identity and started thinking of it as an input to a lookup.

The full chain, in order, with nothing spoiled: **[Overheard at Breakfast on
alzeaty1.github.io](https://alzeaty1.github.io/writeups/overheard-at-breakfast/)**
