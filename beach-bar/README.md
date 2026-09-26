# Beach Bar

**Room:** Beach Bar
**Difficulty:** Easy

## The part worth remembering

RCE is only half of this room. The other half is a root daemon that was started
with its own password sitting in its command-line arguments, where any local user
could read it out of `/proc`.

That is the actual lesson. Deserialization bugs get the CVE-style attention, but
the thing that turned a web foothold into root was an operator passing a secret on
the command line because it was convenient. If you take one thing from the write-up,
take that.

The YAML `load()` on user-supplied input is the boring, expected part. It got me a
shell, and that is all it got me.

**Room:** also covers default credentials, password reuse between accounts, and
the privesc chain that followed.

Full write-up — how the session cookie was captured, how the payload was built, and
the `/proc` step, no flag spoilers: **[alzeaty1.github.io/writeups/beachbar](https://alzeaty1.github.io/writeups/beachbar/)**

## In this folder

- `beachbar_rce.py` — wraps the PyYAML `python/object/apply` payload and scrapes the
  command output back out of the page. Reads the session cookie from a cookiejar dump
  at `/tmp/dj_cookies.txt`; point `URL` at your own instance.

Blank values and a `10.10.10.10` target are deliberate. Work the room first.
