# Packed Light — TryHackMe (Network Forensics)

**Room:** Packed Light · Hacker Holidays: The Byte Lotus Hotel
**Category:** Network Forensics / PCAP Analysis
**Difficulty:** Easy

A keylogger exfiltrates keystrokes hidden inside an HTTP Cookie header, one XOR-encrypted, Base64-encoded character per request.

Full write-up (methodology, how the covert channel was found, no spoilers): **[Read on Medium](https://medium.com/@alzeaty/when-http-cookies-become-a-covert-channel-packed-light-aa6255eddaa5)**

## In this folder

`decode_cookies_teaching_EN.py` — a teaching-version decoder. The key values are left blank on purpose. Work through the hints in the docstring, pull your own Wireshark export, and rebuild the script yourself.

No key, no flag, no shortcuts here. That's the point.
