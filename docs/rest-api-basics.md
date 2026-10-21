# REST API Basics

## What is an API?
An application programming interface (API) is a defined way for one piece of software to request information or actions from another. A web API commonly lets a frontend communicate with a backend server over HTTP.

For example, a weather app might request a forecast from a weather service instead of collecting weather measurements itself.

## What is a REST API?
A REST-style API exposes resources through URLs called **endpoints**. A client sends an HTTP request to an endpoint, and the server returns a response. Many APIs use JSON to represent data.

Example endpoint (illustrative, not a live service):

```text
https://api.example.com/products
```

## Parts of an HTTP request
- **Method:** describes the action the client wants to perform.
- **Endpoint:** identifies the resource.
- **Headers:** provide extra information, such as response format or an authorization token.
- **Body:** carries data for methods such as `POST` or `PATCH`.

| Method | Typical purpose | Example |
|---|---|---|
| `GET` | Read a resource | Retrieve products |
| `POST` | Create a resource or trigger an action | Add a product |
| `PUT` | Replace a resource | Replace a product record |
| `PATCH` | Update part of a resource | Change a product price |
| `DELETE` | Remove a resource | Delete a product |

Exact behavior depends on the API's documentation.

## Example: request data
Run this command in a terminal:

```bash
curl -i https://jsonplaceholder.typicode.com/posts/1
```

The `-i` option displays response headers along with the body. The public sample service returns a post as JSON. A simplified response body could look like this:

```json
{
  "userId": 1,
  "id": 1,
  "title": "A sample post title",
  "body": "A sample post body."
}
```

This JSON is illustrative; the actual response comes from the service.

## Troubleshooting a failed request
1. Check that the URL is spelled correctly.
2. Confirm that the HTTP method matches the API documentation.
3. Read the response status code and error message.
4. Check whether authentication is required.
5. Verify that the request body is valid JSON when a body is required.
6. Consult the API's official documentation before changing parameters.

## Key takeaway
A REST API lets software communicate through documented HTTP endpoints. Understanding the method, endpoint, headers, body, and response makes integration easier to build and debug.
