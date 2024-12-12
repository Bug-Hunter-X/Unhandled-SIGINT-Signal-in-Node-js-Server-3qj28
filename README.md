# Unhandled SIGINT Signal in Node.js Server

This repository demonstrates a common yet often overlooked issue in Node.js: improper handling of the SIGINT (interrupt) signal.  When a server receives a SIGINT signal (e.g., from `Ctrl+C`), it should gracefully shut down to avoid data loss and ensure clean termination. This example shows how to fix it.

## Bug

The `server.js` file contains a simple Node.js HTTP server.  However, it lacks proper handling of the SIGINT signal, resulting in abrupt termination when interrupted.

## Solution

The `serverSolution.js` file demonstrates the correct way to handle the SIGINT signal using the `process.on('SIGINT', ...)` event listener. This allows the server to gracefully close connections and shut down cleanly.

## How to reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `node server.js`.
4. Press `Ctrl+C`. Observe the server's termination.
5. Run `node serverSolution.js`.
6. Press `Ctrl+C`. Observe the graceful shutdown.