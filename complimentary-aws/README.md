# Complimentary

**Room:** Complimentary
**Difficulty:** Easy

**Vulnerability classes:** AWS Cognito identity pool misconfiguration, IAM overprivileged role, DynamoDB Scan exposure

A guest-role identity pool issued credentials whose policy allowed `dynamodb:Scan` against every table in the account. No exploit, no credential theft - the misconfiguration was the vulnerability, and the guest role could read every profile in the app, not just its own.

Full write-up (methodology, payloads, no flag spoilers): **[alzeaty1.github.io/writeups/complimentary-aws](https://alzeaty1.github.io/writeups/complimentary-aws/)**
