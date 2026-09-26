# CryptoCabana

**Room:** CryptoCabana
**Difficulty:** Medium

A SAS token sitting in client-side JavaScript led to a service principal, the service
principal led to a Key Vault, and the vault held four secrets: three key shards and a
`master-key` that returned 403 on every attempt to read its current value.

That 403 is the whole room in one response. The `master-key` is a decoy. What the
room actually wanted was the *version history* of a rotated secret — old secret
versions in Azure Key Vault stay readable after rotation, so the value you want is the
one somebody already replaced.

Chasing the current value of a secret that will not give it up is a good way to burn
an afternoon. Ask what the platform keeps that the owner already forgot.

No payloads here that I would rather you not have. The chain, in order, with the
Azure CLI calls: **[alzeaty1.github.io/writeups/cryptocabana](https://alzeaty1.github.io/writeups/cryptocabana/)**
