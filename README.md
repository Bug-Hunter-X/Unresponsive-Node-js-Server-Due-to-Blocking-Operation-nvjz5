# Unresponsive Node.js Server

This repository demonstrates a common issue in Node.js where a long-running synchronous operation blocks the event loop, making the server unresponsive.  The `bug.js` file shows the problematic code, while `bugSolution.js` provides a solution using asynchronous operations.

## Problem

The `bug.js` file contains a simple HTTP server.  However, it includes a `while` loop that keeps the CPU busy for 5 seconds. During this time, the server cannot handle any new requests. This is because Node.js uses a single-threaded event loop, and a blocking operation prevents the event loop from processing other events.

## Solution

The `bugSolution.js` file demonstrates how to solve this problem by using asynchronous operations.  Asynchronous programming allows the event loop to continue processing other events while the long-running operation is in progress.