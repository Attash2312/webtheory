# AJAX & APIs Theory Cheatsheet

A concise guide to AJAX and API concepts for theory exams. Focuses on how asynchronous web communication works, RESTful APIs, and related web standards.

---

## Table of Contents
- [AJAX \& APIs Theory Cheatsheet](#ajax--apis-theory-cheatsheet)
  - [Table of Contents](#table-of-contents)
  - [What is AJAX?](#what-is-ajax)
  - [How AJAX Works](#how-ajax-works)
  - [XMLHttpRequest vs Fetch API](#xmlhttprequest-vs-fetch-api)
  - [RESTful APIs](#restful-apis)
  - [HTTP Methods \& Status Codes](#http-methods--status-codes)
  - [JSON (JavaScript Object Notation)](#json-javascript-object-notation)
  - [CORS (Cross-Origin Resource Sharing)](#cors-cross-origin-resource-sharing)

---

## What is AJAX?
- **AJAX** stands for Asynchronous JavaScript and XML.
- It is a technique for creating fast, dynamic web pages by making asynchronous requests to the server without reloading the page.
- Modern AJAX uses JSON instead of XML.

## How AJAX Works
1. JavaScript sends a request to the server (using XMLHttpRequest or Fetch API).
2. Server processes the request and sends back a response (often JSON).
3. JavaScript updates the web page dynamically based on the response.

**Benefits:**
- Improves user experience (no full page reloads)
- Enables dynamic, interactive web applications

## XMLHttpRequest vs Fetch API
- **XMLHttpRequest:** Older, more verbose, callback-based.
- **Fetch API:** Modern, promise-based, easier to use, supports async/await.

**XMLHttpRequest Example:**
```js
const xhr = new XMLHttpRequest();
xhr.open('GET', '/api/data');
xhr.onload = function() {
  if (xhr.status === 200) {
    const data = JSON.parse(xhr.responseText);
    console.log(data);
  }
};
xhr.send();
```

**Fetch API Example:**
```js
fetch('/api/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

## RESTful APIs
- **API:** Application Programming Interface; allows communication between different software systems.
- **REST:** Representational State Transfer; an architectural style for designing networked applications.
- **RESTful API:** Uses HTTP methods to perform CRUD operations on resources, typically using JSON.

**Principles:**
- Stateless: Each request contains all information needed
- Resource-based: Each resource has a unique URL
- Uses standard HTTP methods (GET, POST, PUT, DELETE, PATCH)

## HTTP Methods & Status Codes
- **GET:** Retrieve data
- **POST:** Create new data
- **PUT:** Update existing data (replace)
- **PATCH:** Update part of existing data
- **DELETE:** Remove data

**Common Status Codes:**
- 200 OK: Success
- 201 Created: Resource created
- 400 Bad Request: Invalid input
- 401 Unauthorized: Not authenticated
- 403 Forbidden: Not allowed
- 404 Not Found: Resource not found
- 500 Internal Server Error: Server error

## JSON (JavaScript Object Notation)
- Lightweight data-interchange format
- Easy for humans to read and write, and for machines to parse and generate
- Used as the standard data format for AJAX and APIs

**Example:**
```json
{
  "name": "Alice",
  "age": 25,
  "email": "alice@example.com"
}
```

**JavaScript Usage:**
```js
const obj = JSON.parse('{"name":"Alice"}');
const str = JSON.stringify(obj);
```

## CORS (Cross-Origin Resource Sharing)
- **CORS** is a security feature implemented by browsers to restrict web pages from making requests to a different domain than the one that served the web page.
- Servers must send appropriate headers (e.g., `Access-Control-Allow-Origin`) to allow cross-origin requests.

**Example:**
```http
Access-Control-Allow-Origin: *
```

**How to handle CORS in Express:**
```js
const cors = require('cors');
app.use(cors());
```

---

This cheatsheet covers the most important AJAX and API theory for exams. Focus on understanding how asynchronous requests work, RESTful principles, and HTTP standards! 