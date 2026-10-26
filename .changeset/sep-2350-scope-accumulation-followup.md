---
'@modelcontextprotocol/client': patch
---

When a refresh is refused (`invalid_grant` or `invalid_dpop_proof`) and `auth()` drops the stored tokens, the new authorization request now also asks for the scope that grant held, so permissions granted earlier through step-up survive. Values the authorization server does not list in `scopes_supported` are left out, and the scope is asked for only once: if the server refuses it, the next authorization asks for the challenged scope alone.
