# Common HTTP Status Codes

HTTP status codes are three-digit numbers that summarize the result of an HTTP request. They are grouped by their first digit.

| Code | Meaning | What it usually tells you |
|---|---|---|
| `200 OK` | Success | The request worked |
| `201 Created` | Resource created | A new resource was created |
| `204 No Content` | Success without a response body | The request succeeded, but there is no body to return |
| `301 Moved Permanently` | Redirect | The resource has a new permanent URL |
| `400 Bad Request` | Invalid request | Check the request format and parameters |
| `401 Unauthorized` | Authentication missing or invalid | Check credentials or authorization headers |
| `403 Forbidden` | Access denied | The server refuses access |
| `404 Not Found` | Resource not found | Check the endpoint and resource identifier |
| `409 Conflict` | Conflict with current state | The operation may conflict with existing data |
| `422 Unprocessable Content` | Request rejected by validation | Check submitted values and validation rules |
| `429 Too Many Requests` | Rate limit reached | Wait and follow the API's retry guidance |
| `500 Internal Server Error` | Server-side failure | The server encountered an unexpected condition |
| `503 Service Unavailable` | Temporarily unavailable | The service may be overloaded or under maintenance |

An API may provide more specific details in its documentation or response body.

## A simple debugging workflow
1. **Read the code.** Decide whether the request succeeded, needs correction, or failed on the server.
2. **Read the response body.** It may explain the problem.
3. **Check your request.** Verify the URL, method, headers, authentication, and body.
4. **Avoid blind retries.** Follow guidance for rate limits or temporary failures. Be careful retrying operations that create payments or other important changes.
5. **Record the result.** When reporting a bug, include the endpoint, method, status code, and a redacted error message. Never share passwords, tokens, or private user data.

## Example: 404 Not Found
First check for a typo in the endpoint. If the endpoint is correct, confirm that the requested record exists and that the API uses the identifier as expected.

## Key takeaway
A status code is a starting point, not always a complete diagnosis. Combine it with the response body and API documentation to understand what happened.
