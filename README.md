# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js applications where a long-running request can cause the server to become unresponsive to new requests.  The example uses a simple HTTP server that simulates a long-running task.  This blocking behavior is a result of Node.js's single-threaded event loop.  The solution explores using asynchronous operations to prevent this blocking issue.

## Setup

1. Clone this repository.
2. Run `npm install`

## Running the Buggy Code

1. Execute `node server.js`
2. Open multiple browser tabs and try to access `http://localhost:3000`  You'll observe the server fails to respond to subsequent requests while the long task is running.

## Running the Solution

1. Execute `node server-solution.js`
2. Repeat step 2 from the previous section.  You'll find the server now responds to concurrent requests without issue.

This is because the solution utilizes asynchronous operations, enabling the event loop to continue handling new events even during the execution of lengthy tasks.