# Complimentary

**Room:** Complimentary
**Difficulty:** Easy

No exploit here, and that is the interesting part.

The app used a Cognito identity pool with an unauthenticated "guest" role, and the
policy attached to that role allowed `dynamodb:Scan` across the account. So the chain
was: request guest credentials from the public pool, attach them to the AWS CLI, scan
the tables, read other people's records. Every step is a documented API call. Nothing
was broken except the policy.

The lesson is narrow and worth stating plainly — a Scan permission is a data
disclosure permission. "Read-only" is not a safety property when the read is
unscoped and unauthenticated.

The reasoning, the exact policy that gives it away, and how I checked the blast
radius without touching anything I shouldn't have: **[the write-up on
alzeaty1.github.io](https://alzeaty1.github.io/writeups/complimentary-aws/)**
