---
title: Operations and status codes
weight: 7
---

The following is guidelines prescribing what HTTP method to use for common "business functions" and what status codes to return for the happy case. If a header is to be returned, an example is given.

| Function | HTTP Method | Status Code | Header   | Comment |
|----------|-------------|-------------|----------|---------|
| List     | GET /foos/  | 200 OK |  | Collection in response. 200 Ok even if empty collection |
| Create   | POST /foos/ | 201 Created | Location: /foos/1234 | No body in response |
| Get      | GET /foos/1234 | 200 OK   |          | |
| Update   | PUT /foos/1234 | 204 No Content | | No body in response |
| Update (patch) | PATCH /foos/1234 | 200 OK | | The updated resource in response body |
| Delete   | DELETE /foos/1234 | 204 No Content | | No body in response |

## References
<a href="https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html" target="_blank">Method definitions</a>  
<a href="https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" target="_blank">Status Code Definitions</a>  
<a href="https://tools.ietf.org/html/rfc6902" target="_blank">JSON Patch</a>  
