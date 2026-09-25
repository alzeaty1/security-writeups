# XSS Introduction

**Room:** XSS Introduction
**Difficulty:** Easy

**Vulnerability classes:** Cross-Site Scripting (Reflected, Stored, DOM-based, Blind), Insufficient Output Encoding, Inadequate Input Validation, Missing Content Security Policy

One idea, four shapes: the app takes input and renders it without filtering or encoding correctly. Reflected and stored come back in the page; DOM-based never touches the server; blind fires without any visible output at all.

Full write-up (methodology, payloads, no flag spoilers): **[alzeaty1.github.io/writeups/xss-introduction](https://alzeaty1.github.io/writeups/xss-introduction/)**
