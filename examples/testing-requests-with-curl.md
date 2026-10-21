# Testing API Requests with curl

`curl` is a command-line tool for sending requests to URLs. It is useful for checking an API before writing frontend code.

## Before you start
Install curl if it is not already available. Recent Windows, macOS, and Linux systems commonly include it. Open PowerShell, Terminal, or another command-line shell.

## 1. Send a GET request
Run:

```bash
curl -i https://jsonplaceholder.typicode.com/posts/1
```

This sends a GET request to a public sample API. The `-i` flag includes response headers so you can see the status code.

## 2. Send a POST request with JSON
Run:

```bash
curl -i -X POST https://jsonplaceholder.typicode.com/posts \
  -H "Content-Type: application/json" \
  -d '{"title":"My test post","body":"Learning API requests","userId":1}'
```

- `-X POST` specifies the HTTP method.
- `-H` adds a request header.
- `-d` supplies the request body.

The sample service is intended for testing and may simulate writes rather than permanently storing data.

## 3. Interpret the result
Look for the HTTP status code near the beginning of the response. Then inspect the JSON body for returned data or an error message.

If the command fails:
- Check your internet connection and the URL.
- Make sure JSON property names and string values use double quotes.
- Check whether your shell interprets quotes or line breaks differently.
- Read the API documentation for required headers or authentication.

## Security note
Do not paste passwords, API keys, access tokens, or private data into public repositories or screenshots. Keep secrets out of source control.

## Practice
1. Change the final number in the GET URL from `1` to `2`.
2. Compare the returned JSON.
3. Try removing `-i` and observe how the output changes.
4. Write down the status code and explain it in your own words.
