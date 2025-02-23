# Node.js Server Unresponsiveness

This repository demonstrates a common Node.js issue: server unresponsiveness caused by a long-running synchronous operation within the request handler.  The `server.js` file contains a server that simulates a long-running task, blocking the event loop and making the server unresponsive.

The `serverSolution.js` file provides a solution by using asynchronous operations and a worker thread to avoid blocking the main thread.

## How to reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `node server.js`.
4. Try to access the server (e.g., using `curl http://localhost:3000` or a browser).
5. Observe that the server is unresponsive for 5 seconds. 

## Solution

The solution involves using asynchronous operations (like promises or async/await) or offloading the long-running task to a worker thread.  See `serverSolution.js` for a demonstration of asynchronous task processing using promises.