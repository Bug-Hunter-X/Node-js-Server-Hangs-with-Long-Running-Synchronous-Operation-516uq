# Node.js Server Hang - Synchronous Operation

This repository demonstrates a common Node.js issue: a server hanging due to a long-running synchronous operation blocking the event loop.

The `server.js` file contains the buggy code.  The `serverSolution.js` file shows the corrected code using asynchronous operations.

## Bug
The server performs a 5-second CPU-bound operation synchronously within the request handler.  During this time, the event loop is blocked, and the server becomes unresponsive to new requests.

## Solution
The solution involves refactoring the code to use asynchronous operations (e.g., using `setTimeout` or promises). This allows other events to be processed while the long-running task executes in the background without blocking the event loop.