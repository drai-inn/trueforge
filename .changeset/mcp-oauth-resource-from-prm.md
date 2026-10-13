---
'@truefoundry/trueforge': patch
---

MCP OAuth (DCR) now requests tokens for the RFC 8707 `resource` an MCP server advertises in its RFC 9728 Protected Resource Metadata, when that resource covers the server URL, instead of always using the server URL. Servers that audience-bind tokens to a base URL, such as Coder's MCP endpoint, now accept the tokens. Existing DCR servers record their resource on first use without re-registering; if it differs from the server URL, their users reconnect once. Registering a server whose advertised resource does not cover its URL is now refused.
