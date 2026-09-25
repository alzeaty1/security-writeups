# CryptoCabana

**Room:** CryptoCabana
**Difficulty:** Medium

**Vulnerability classes:** Exposed cloud credentials, Azure Blob Storage SAS token, Service principal abuse, Azure Key Vault, Secret rotation

A SAS token in client-side JavaScript led to an Azure service principal, which led to a Key Vault holding three key shards and one `master-key` that returned 403. The prize was in a rotated secret's version history, not in the current value.

Full write-up (methodology, payloads, no flag spoilers): **[alzeaty1.github.io/writeups/cryptocabana](https://alzeaty1.github.io/writeups/cryptocabana/)**
