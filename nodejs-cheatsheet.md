# Node.js Theory Cheatsheet

A concise guide to Node.js concepts for theory exams. Focuses on architecture, core ideas, and practical understanding.

---

## Table of Contents
- [What is Node.js?](#what-is-nodejs)
- [Node.js Architecture](#nodejs-architecture)
- [Event Loop & Asynchronous Programming](#event-loop--asynchronous-programming)
- [Modules & npm](#modules--npm)
- [Core Modules](#core-modules)
- [Error Handling](#error-handling)
- [Common Use Cases](#common-use-cases)
- [Sample Code Snippets](#sample-code-snippets)

---

## What is Node.js?
- Node.js is a runtime environment that allows you to run JavaScript on the server (outside the browser).
- Built on Chrome's V8 JavaScript engine.
- Enables building scalable, high-performance network applications.
- Uses an event-driven, non-blocking I/O model.

## Node.js Architecture
- **Single-threaded** but handles many connections concurrently using the event loop.
- **Non-blocking I/O:** Operations like file reading, network requests, and database queries do not block the main thread.
- **Event-driven:** Uses events and callbacks to handle asynchronous operations.

**Diagram:**
```
Client Request -> Event Queue -> Event Loop -> Thread Pool (for I/O) -> Callback
```

## Event Loop & Asynchronous Programming
- The event loop is the core of Node.js's non-blocking architecture.
- Handles multiple operations by offloading I/O to the system and using callbacks/promises to process results.

**Phases of the Event Loop:**
1. Timers (setTimeout, setInterval)
2. I/O callbacks
3. Idle, prepare
4. Poll (new I/O events)
5. Check (setImmediate)
6. Close callbacks

**Example:**
```js
console.log('Start');
setTimeout(() => console.log('Timeout'), 0);
console.log('End');
// Output: Start, End, Timeout
```

## Modules & npm
- **Modules:** Reusable blocks of code. Node.js uses CommonJS module system (`require`, `module.exports`).
- **npm:** Node Package Manager. Used to install, share, and manage third-party packages.

**Types of Modules:**
- Core modules (built-in)
- Local modules (your own files)
- Third-party modules (from npm)

**Example:**
```js
// math.js
exports.add = (a, b) => a + b;

// app.js
const math = require('./math');
console.log(math.add(2, 3));
```

## Core Modules
- **fs:** File system operations
- **http:** Create web servers
- **path:** File and directory paths
- **os:** Operating system info
- **events:** Event emitter for custom events

**Example:**
```js
const fs = require('fs');
fs.readFile('file.txt', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data);
});
```

## Error Handling
- Always handle errors in async code (callbacks: `err` parameter, promises: `.catch()`, try/catch for sync/async-await).
- Unhandled errors can crash the process.

**Example:**
```js
// Callback error handling
fs.readFile('nofile.txt', 'utf8', (err, data) => {
  if (err) {
    console.error('Error:', err.message);
    return;
  }
  console.log(data);
});

// Promise error handling
someAsyncFunction()
  .then(result => console.log(result))
  .catch(err => console.error('Error:', err));

// try/catch with async/await
async function readFile() {
  try {
    const data = await fs.promises.readFile('file.txt', 'utf8');
    console.log(data);
  } catch (err) {
    console.error('Error:', err);
  }
}
```

## Common Use Cases
- Web servers (Express.js)
- RESTful APIs
- Real-time apps (chat, games)
- File system tools
- Command-line utilities
- Proxies and middleware

## Sample Code Snippets

**Simple HTTP Server:**
```js
const http = require('http');
const server = http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('Hello, Node.js!');
});
server.listen(3000, () => console.log('Server running on port 3000'));
```

**Event Emitter:**
```js
const EventEmitter = require('events');
const emitter = new EventEmitter();
emitter.on('greet', name => console.log(`Hello, ${name}`));
emitter.emit('greet', 'Alice');
```

---

This cheatsheet covers the most important Node.js theory for exams. Focus on understanding the architecture, event loop, modules, and error handling! 