---
'@modelcontextprotocol/sdk': patch
---

Reject authorization server metadata whose `issuer` does not match the URL it was discovered for (RFC 8414 §3.3). `discoverAuthorizationServerMetadata()` now throws `IssuerMismatchError` instead of returning a document that names a different issuer, so `auth()` stops before using
that metadata or posting credentials to its endpoints. `skipIssuerValidation: true` opts out for known-misconfigured authorization servers.
