# Do Not Disturb

**Room:** Do Not Disturb
**Difficulty:** Medium

Four flaws, in this order:

1. A MongoDB-backed login that trusted the query object. `{"$ne": ""}` is not a
   password, it is a comparison that is true of every document that has a password.
   No guessing, no wordlist, no rate limit to fight.
2. EJS template injection on the way to RCE.
3. The shell that came back had a Node inspector bound to loopback — reachable by
   port-forwarding, because loopback is only a boundary from outside the box.
4. Two escalations after that: a service account, then `debugfs` reading the raw block
   device straight off disk.

The dead ends were worth as much as the wins. `execSync` kept failing with
`Bad fd number`, and the reason is that `>/dev/tcp/...` redirection is a **bash**
feature — the child was being run through `dash`, which cannot parse it. The fix is
not another payload, it is specifying the shell you actually meant. I lost time to
that one and wrote it down so nobody else has to.

**Methodology, payload construction, both escalations, no flag spoilers:** the full
write-up lives at
**[alzeaty1.github.io/writeups/dodonturb](https://alzeaty1.github.io/writeups/dodonturb/)**

Nothing in this folder is a script, which is intentional — the interesting part of
this room is the sequence, not a single repeatable action.
