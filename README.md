# Express.js - Empty or Invalid JSON Request Body Handling

This repository demonstrates a common issue in Express.js applications where the server fails to gracefully handle empty or invalid JSON request bodies.  The application uses `express.json()` middleware to parse JSON requests, but it doesn't include error handling for scenarios where the request body is malformed or missing.

## Bug

The `bug.js` file contains the buggy code.  When an empty or invalid JSON request is sent to the `/data` endpoint, the server logs an empty object `{}` in the console and sends a 'Data received' response, masking the actual error.

## Solution

The `bugSolution.js` file provides a corrected version that includes proper error handling using a try-catch block.  It catches JSON parsing errors and sends an appropriate error response to the client, providing more informative feedback when an issue arises.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository's directory.
3. Run `npm install` to install the dependencies.
4. Run `node bug.js` to start the buggy server.
5. Send an empty POST request or a POST request with invalid JSON to `http://localhost:3000/data` using a tool like Postman or curl.
6. Observe the server's response and console output.
7. Repeat steps 4-6 with `node bugSolution.js` to see the improved error handling.
