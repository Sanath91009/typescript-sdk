---
'@modelcontextprotocol/sdk': patch
---

The Streamable HTTP and SSE client transports now merge `requestInit.headers` case-insensitively. A caller that set `MCP-Protocol-Version` (or `Authorization`, or `Mcp-Session-Id`) in a different case from the transport's own spelling no longer gets both entries sent as one comma-separated header, which the server rejected with a 400. The transport's negotiated values are set on top of the caller's headers, so they replace a same-named entry whatever its spelling.
