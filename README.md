# Node.js Server Error Handling Bug

This repository demonstrates a common bug in Node.js server development: improper error handling for non-existent routes. The initial code doesn't handle requests to different endpoints other than / correctly, causing unexpected behavior. The solution demonstrates the correct way to return 404 status codes for non-existent pages.

## Bug

The bug lies in the `http.createServer` function.  It only handles requests to the root URL ('/').  Any other request results in a default 404 behavior from the Node.js http server, but this is not explicitly managed by the application code.  This can lead to inconsistent behavior and unexpected responses to the client.

## Solution

The solution explicitly handles requests to other URLs using `req.url` to identify the requested path and return an appropriate 404 response with the correct status code and message.