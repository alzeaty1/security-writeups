# XSS Introduction

**Room:** XSS Introduction
**Difficulty:** Easy

One bug, four shapes.

The application takes input and renders it without encoding it, and where the input
goes decides which kind of XSS you are looking at:

- **Reflected** — your payload comes straight back in the response.
- **Stored** — it was saved and comes back for everyone, including you, which makes
  it the one that turns into someone else's problem.
- **DOM-based** — never touches the server at all. The sink is in the JavaScript, so
  nothing in the request log will ever show you what happened.
- **Blind** — fires with no visible output. You confirm it out of band and nothing on
  the page changes.

The ordering is not arbitrary. Reflected and stored are the same flaw in different
places; DOM-based is the same flaw with the server removed from the loop; blind is the
same flaw with the confirmation channel moved. Learn where the data lands and you can
name the vulnerability before you fire anything.

**Payload construction and how I verified each variant, no flag spoilers:**
**[alzeaty1.github.io/writeups/xss-introduction](https://alzeaty1.github.io/writeups/xss-introduction/)**
