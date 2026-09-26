# Security Writeups

Lab write-ups from self-directed work, mostly TryHackMe, plus a PortSwigger SQLi
practical. The reasoning lives on the site — the full methodology, the payloads, the
parts where I went wrong first — and this repo is the index and the scripts.

Nine rooms, and they are not nine unrelated things. What they share is that almost
none of them needed a novel exploit. What they have in common:

- **Misconfiguration did most of the work.** A `.git` directory on a web root. A
  password in a daemon's command-line arguments. A Cognito guest role with
  `dynamodb:Scan` on everything. A loopback-bound inspector that only looked safe.
- **The boring ones needed patience more than tools.** Boolean and time-based blind
  SQLi are one character per request. CryptoCabana was not a crypto problem at all —
  the secret was never the value, it was the version history.
- **The chaining is the content.** None of these rooms are solved in one step, and
  the write-ups spend most of their length on how step two was even possible after
  step one.

Coverage across the set: web exploitation (SQLi, XSS, SSTI, deserialization), cloud
credential abuse on both AWS and Azure, network forensics, and OSINT that never
touched a server at all.

## The teaching-script convention

Some folders ship a Python script. In every case it is a **teaching version**: the
key values, targets, and query templates are left blank or as obvious placeholders on
purpose.

The reasoning is simple. A script that works out of the box against a live instance
teaches you the invocation, not the mechanism, and it ages badly. If you open
`beachbar_rce.py` and it runs, you have learned nothing about why the payload works.
Fill in the blanks from your own traffic, or you have skipped the part that mattered.

## Rooms

| Room | What it actually was | Difficulty |
|---|---|---|
| [Beach Bar](./beach-bar) | PyYAML deserialization RCE, then a root daemon that leaked its own password via `/proc` | Easy |
| [Complimentary](./complimentary-aws) | An unauthenticated Cognito role allowed to `Scan` every table | Easy |
| [CryptoCabana](./cryptocabana) | Azure SAS token to service principal to Key Vault — and a rotated secret's version history | Medium |
| [Do Not Disturb](./do-not-disturb) | `{"$ne": ""}` login bypass, EJS template injection, loopback Node inspector, two escalations | Medium |
| [Overheard at Breakfast](./overheard-at-breakfast) | An email as an MD5 input to Gravatar, and no server to attack at all | Easy |
| [Packed Light](./packed-light) | A keylogger exfiltrating keystrokes one XOR'd cookie at a time | Easy |
| [Room 404](./room-404) | The repository served to anyone who asked for it | Easy |
| [SQL Injection](./sqli) | Four oracles, one endpoint | Easy |
| [XSS Introduction](./xss-introduction) | One encoding bug in four shapes, ending with blind | Easy |

## Elsewhere

- Write-ups: **[alzeaty1.github.io](https://alzeaty1.github.io/)**
- [ctf-crypto-analysis-tool](https://github.com/alzeaty1/ctf-crypto-analysis-tool) — modular crypto analysis CLI (XOR, entropy, ECB detection)
- TryHackMe: [tryhackme.com/p/ALZeaty](https://tryhackme.com/p/ALZeaty)
- LinkedIn: [Ahmed Abdalrhman](https://www.linkedin.com/in/ahmed-abdalrhman838/)

## About

Junior penetration tester. Self-directed lab work across web application security, network analysis, and cloud credential abuse (AWS and Azure). Certified through NTI/NTRA (Cybersecurity Academy) and TryHackMe Advent of Cyber 2025 (24 challenges).

## License

MIT
