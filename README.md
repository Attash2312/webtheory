# Web Technologies Cheatsheet

A comprehensive guide for web development theory and practicals, from beginner to MERN stack. Includes conceptual explanations, code snippets, practice questions, and solutions.

---

## Table of Contents
- [Web Technologies Cheatsheet](#web-technologies-cheatsheet)
  - [Table of Contents](#table-of-contents)
  - [HTML Basics](#html-basics)
    - [Key Concepts](#key-concepts)
    - [Example: Basic HTML Structure](#example-basic-html-structure)
    - [Practice Question](#practice-question)
  - [CSS Fundamentals](#css-fundamentals)
    - [Key Concepts](#key-concepts-1)
    - [Example: Responsive Flexbox Layout](#example-responsive-flexbox-layout)
    - [Practice Question](#practice-question-1)
  - [JavaScript Essentials](#javascript-essentials)
    - [Key Concepts](#key-concepts-2)
    - [Example: Basic JavaScript](#example-basic-javascript)
    - [Practice Question](#practice-question-2)
  - [Advanced JavaScript](#advanced-javascript)
    - [Key Concepts](#key-concepts-3)
    - [Example: Closures](#example-closures)
    - [Example: Promises \& Async/Await](#example-promises--asyncawait)
    - [Practice Question](#practice-question-3)
  - [Version Control (Git)](#version-control-git)
    - [Key Concepts](#key-concepts-4)
    - [Common Commands](#common-commands)
    - [Practice Question](#practice-question-4)
  - [Responsive Design](#responsive-design)
    - [Key Concepts](#key-concepts-5)
    - [Example: Media Query](#example-media-query)
    - [Practice Question](#practice-question-5)
  - [Node.js \& Backend Basics](#nodejs--backend-basics)
    - [Key Concepts](#key-concepts-6)
    - [Example: Simple HTTP Server](#example-simple-http-server)
    - [Practice Question](#practice-question-6)
  - [Express.js](#expressjs)
    - [Key Concepts](#key-concepts-7)
    - [Example: Basic Express App](#example-basic-express-app)
    - [Practice Question](#practice-question-7)
  - [Databases (MongoDB)](#databases-mongodb)
    - [Key Concepts](#key-concepts-8)
    - [Example: MongoDB with Mongoose](#example-mongodb-with-mongoose)
    - [Practice Question](#practice-question-8)
  - [MERN Stack Integration](#mern-stack-integration)
    - [Key Concepts](#key-concepts-9)
    - [Example: MERN Integration](#example-mern-integration)
    - [Practice Question](#practice-question-9)
  - [APIs \& REST](#apis--rest)
    - [Key Concepts](#key-concepts-10)
    - [Example: RESTful API](#example-restful-api)
    - [Practice Question](#practice-question-10)
  - [Authentication \& Security](#authentication--security)
    - [Key Concepts](#key-concepts-11)
    - [Example: JWT Authentication](#example-jwt-authentication)
    - [Practice Question](#practice-question-11)
  - [Deployment](#deployment)
    - [Key Concepts](#key-concepts-12)
    - [Example: Environment Variables](#example-environment-variables)
    - [Example: PM2 Configuration](#example-pm2-configuration)
    - [Practice Question](#practice-question-12)
  - [Enhanced EJS \& MVC Practical Examples](#enhanced-ejs--mvc-practical-examples)
    - [Advanced EJS Features](#advanced-ejs-features)
    - [MVC Implementation](#mvc-implementation)
    - [Practice Question](#practice-question-13)
  - [Frontend Frameworks (React - Intro)](#frontend-frameworks-react---intro)
    - [Key Concepts \& Theory](#key-concepts--theory)
    - [Example: React Component with Hooks](#example-react-component-with-hooks)
    - [Practice Question](#practice-question-14)
  - [Advanced JavaScript (Expanded)](#advanced-javascript-expanded)
    - [ES6+ Features (Detailed)](#es6-features-detailed)
    - [Prototypes and Inheritance (Theory)](#prototypes-and-inheritance-theory)
    - [Error Handling (Detailed)](#error-handling-detailed)
    - [Modules (ES6 Modules)](#modules-es6-modules)
    - [Practice Question](#practice-question-15)
  - [Enhanced Theory Concepts](#enhanced-theory-concepts)
    - [JavaScript Event Loop (Theory)](#javascript-event-loop-theory)
    - [Memory Management (Theory)](#memory-management-theory)
    - [CSS Box Model (Detailed Theory)](#css-box-model-detailed-theory)
    - [HTTP Protocol (Theory)](#http-protocol-theory)
    - [Database Normalization (Theory)](#database-normalization-theory)
    - [Practice Question](#practice-question-16)
  - [Advanced Web Development Theory](#advanced-web-development-theory)
    - [Web Performance Optimization (Theory)](#web-performance-optimization-theory)
    - [Design Patterns in Web Development](#design-patterns-in-web-development)
    - [Security Best Practices (Theory)](#security-best-practices-theory)
    - [Progressive Web Apps (PWA) Theory](#progressive-web-apps-pwa-theory)
    - [Microservices Architecture (Theory)](#microservices-architecture-theory)
    - [State Management Patterns](#state-management-patterns)
    - [Testing Strategies (Theory)](#testing-strategies-theory)
    - [Web Accessibility (A11y) Theory](#web-accessibility-a11y-theory)
    - [Web APIs and Browser Capabilities](#web-apis-and-browser-capabilities)
    - [Practice Question](#practice-question-17)

---

## HTML Basics

### Key Concepts
- **HTML (HyperText Markup Language):** The standard language for creating web pages.
- **Elements & Tags:** HTML uses tags like `<html>`, `<head>`, `<body>`, `<h1>`, `<p>`, etc.
- **Attributes:** Provide additional information about elements (e.g., `<img src="image.jpg" alt="desc">`).
- **Semantic HTML:** Tags that convey meaning (e.g., `<header>`, `<nav>`, `<main>`, `<footer>`, `<article>`, `<section>`).
- **Forms:** Used for user input (`<form>`, `<input>`, `<textarea>`, `<button>`, etc.).
- **Accessibility:** Use `alt`, `aria-*` attributes, and semantic tags for better accessibility.

### Example: Basic HTML Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Sample Page</title>
</head>
<body>
  <header>
    <h1>Welcome to My Website</h1>
  </header>
  <nav>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
  </nav>
  <main>
    <section id="about">
      <h2>About</h2>
      <p>This is a sample website.</p>
    </section>
    <section id="contact">
      <h2>Contact</h2>
      <form>
        <label for="name">Name:</label>
        <input type="text" id="name" name="name">
        <button type="submit">Submit</button>
      </form>
    </section>
  </main>
  <footer>
    <p>&copy; 2024 My Website</p>
  </footer>
</body>
</html>
```

### Practice Question
**Q:** What is the difference between `<div>` and `<section>`?

**Solution:**  
- `<div>` is a generic container with no semantic meaning, used for grouping elements for styling or scripting.
- `<section>` is a semantic element that represents a standalone section of content, typically with a heading.

**Explanation:**  
Use `<section>` when the content is a distinct part of your document (like a chapter or a group of related content). Use `<div>` for layout or styling when no semantic meaning is needed.

---

## CSS Fundamentals

### Key Concepts
- **Selectors:** Target HTML elements (`.class`, `#id`, `element`).
- **Box Model:** Content, padding, border, margin.
- **Flexbox & Grid:** Modern layout systems.
- **Responsive Design:** Media queries for different screen sizes.
- **Colors, Fonts, and Units:** `px`, `em`, `rem`, `%`, `vw`, `vh`.
- **Pseudo-classes/elements:** `:hover`, `:active`, `::before`, `::after`.

### Example: Responsive Flexbox Layout
```css
.container {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
}
.item {
  flex: 1 1 200px;
  background: #f0f0f0;
  padding: 20px;
}
@media (max-width: 600px) {
  .container {
    flex-direction: column;
  }
}
```

### Practice Question
**Q:** What is the difference between `margin` and `padding`?

**Solution:**  
- `margin` is the space outside the border of an element.
- `padding` is the space between the content and the border of an element.

**Explanation:**  
`margin` separates elements from each other, while `padding` creates space inside the element, around its content.

---

## JavaScript Essentials

### Key Concepts
- **Variables:** `var`, `let`, `const`
- **Data Types:** String, Number, Boolean, Object, Array, Null, Undefined
- **Operators:** `+`, `-`, `*`, `/`, `==`, `===`, `!=`, `!==`, `&&`, `||`, etc.
- **Control Flow:** `if`, `else`, `switch`, `for`, `while`, `do...while`
- **Functions:** Declaration, expression, arrow functions
- **Events:** Handling user actions (e.g., `onclick`)
- **DOM Manipulation:** Access and modify HTML elements

### Example: Basic JavaScript
```js
// Variable declaration
let name = "Alice";
const age = 25;

// Function
function greet(user) {
  return `Hello, ${user}!`;
}

// Event Listener
document.getElementById("myBtn").addEventListener("click", function() {
  alert(greet(name));
});
```

### Practice Question
**Q:** What is the difference between `let`, `const`, and `var`?

**Solution:**  
- `var` is function-scoped and can be redeclared/updated.
- `let` is block-scoped and can be updated but not redeclared in the same scope.
- `const` is block-scoped and cannot be updated or redeclared.

**Explanation:**  
Prefer `let` and `const` for modern JS. Use `const` for values that won't change, and `let` for variables that will.

---

This is a good amount for one prompt.  
Say "next" to continue with Advanced JavaScript, Version Control (Git), Responsive Design, Node.js & Backend, Express.js, MongoDB, MERN, APIs, Auth/Security, Deployment, and more EJS/MVC practicals!

## Advanced JavaScript

### Key Concepts
- **Closures:** Functions that remember their lexical scope even when executed outside it.
- **Callbacks:** Functions passed as arguments to other functions.
- **Promises:** Objects representing the eventual completion (or failure) of an async operation.
- **Async/Await:** Syntactic sugar for working with Promises.
- **ES6+ Features:** Arrow functions, destructuring, spread/rest, template literals, classes, modules.
- **Prototypes & Inheritance:** JavaScript's object inheritance model.
- **Error Handling:** `try...catch`, custom errors.

### Example: Closures
```js
function makeCounter() {
  let count = 0;
  return function() {
    count++;
    return count;
  };
}
const counter = makeCounter();
console.log(counter()); // 1
console.log(counter()); // 2
```

### Example: Promises & Async/Await
```js
function fetchData() {
  return new Promise((resolve) => {
    setTimeout(() => resolve("Data loaded!"), 1000);
  });
}

async function showData() {
  const data = await fetchData();
  console.log(data);
}
showData(); // Data loaded!
```

### Practice Question
**Q:** What is a closure? Give an example.

**Solution:**  
A closure is a function that retains access to its lexical scope, even when the function is executed outside that scope.

**Example:**
```js
function outer() {
  let x = 10;
  return function inner() {
    return x;
  };
}
const getX = outer();
console.log(getX()); // 10
```

**Explanation:**  
The `inner` function "closes over" the variable `x` from its parent scope.

---

## Version Control (Git)

### Key Concepts
- **Repository:** A project tracked by Git.
- **Commit:** A snapshot of changes.
- **Branch:** A parallel version of the repository.
- **Merge:** Combine changes from different branches.
- **Clone, Pull, Push:** Copy, fetch, and send changes to remote repositories.
- **Versioning:** Tagging releases, semantic versioning.

### Common Commands
```bash
git init                # Initialize a new repo
git clone <url>         # Clone a repo
git status              # Check status
git add .               # Stage changes
git commit -m "msg"     # Commit changes
git branch              # List branches
git checkout -b feature # Create/switch to branch
git merge feature       # Merge branch
git pull                # Fetch and merge from remote
git push                # Push to remote
git tag v1.0.0          # Tag a release
```

### Practice Question
**Q:** What is the difference between `git merge` and `git rebase`?

**Solution:**  
- `git merge` combines histories, creating a merge commit.
- `git rebase` moves or reapplies commits on top of another base, creating a linear history.

**Explanation:**  
Use `merge` for preserving history, `rebase` for a cleaner, linear history.

---

## Responsive Design

### Key Concepts
- **Media Queries:** CSS rules for different screen sizes.
- **Mobile-First:** Design for mobile, then scale up.
- **Flexible Layouts:** Use relative units (`%`, `em`, `rem`, `vw`, `vh`).
- **Images:** Responsive images with `max-width: 100%`.

### Example: Media Query
```css
body {
  font-size: 18px;
}
@media (max-width: 600px) {
  body {
    font-size: 16px;
  }
}
```

### Practice Question
**Q:** What is a media query? Give an example.

**Solution:**  
A media query applies CSS styles based on device characteristics like width.

**Example:**
```css
@media (max-width: 800px) {
  .sidebar { display: none; }
}
```

**Explanation:**  
This hides the sidebar on screens 800px wide or less.

---

## Node.js & Backend Basics

### Key Concepts
- **Node.js:** JavaScript runtime for server-side programming.
- **Modules:** Reusable code files (`require`, `module.exports`).
- **npm:** Node package manager.
- **File System:** Read/write files with `fs` module.
- **Event Loop:** Handles async operations.

### Example: Simple HTTP Server
```js
const http = require('http');
const server = http.createServer((req, res) => {
  res.writeHead(200, {'Content-Type': 'text/plain'});
  res.end('Hello, world!');
});
server.listen(3000, () => console.log('Server running'));
```

### Practice Question
**Q:** What is the purpose of `module.exports` in Node.js?

**Solution:**  
It allows you to export functions, objects, or values from a file so they can be used in other files via `require`.

**Explanation:**  
This enables modular code organization in Node.js.

---

## Express.js

### Key Concepts
- **Express:** Minimalist web framework for Node.js.
- **Routing:** Define endpoints for HTTP methods.
- **Middleware:** Functions that process requests.
- **Error Handling:** Custom error middleware.
- **REST APIs:** Build APIs with Express.

### Example: Basic Express App
```js
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello from Express!');
});

app.listen(3000, () => console.log('Server started'));
```

### Practice Question
**Q:** What is middleware in Express?

**Solution:**  
Middleware is a function that has access to the request, response, and next middleware in the app's request-response cycle.

**Explanation:**  
Middleware can modify requests/responses, end the request, or pass control to the next function.

---

Say "next" to continue with MongoDB, MERN Stack, APIs & REST, Authentication & Security, Deployment, and more EJS/MVC practicals!

## Databases (MongoDB)

### Key Concepts
- **MongoDB:** NoSQL document database.
- **Collections:** Groups of documents (similar to tables in SQL).
- **Documents:** JSON-like objects stored in collections.
- **CRUD Operations:** Create, Read, Update, Delete.
- **Mongoose:** Object Data Modeling (ODM) library for MongoDB.
- **Schema:** Define structure and validation for documents.

### Example: MongoDB with Mongoose
```js
const mongoose = require('mongoose');
const userSchema = new mongoose.Schema({
  name: { type: String, required: true },
  email: { type: String, unique: true },
  age: Number
});
const User = mongoose.model('User', userSchema);

// Create
const user = new User({ name: 'Alice', email: 'alice@example.com' });
await user.save();

// Read
const users = await User.find({ age: { $gte: 18 } });

// Update
await User.updateOne({ name: 'Alice' }, { age: 25 });

// Delete
await User.deleteOne({ name: 'Alice' });
```

### Practice Question
**Q:** What is the difference between SQL and NoSQL databases?

**Solution:**  
- SQL databases are relational, use structured query language, and have predefined schemas.
- NoSQL databases are non-relational, use various data models, and have flexible schemas.

**Explanation:**  
MongoDB is NoSQL, storing data as documents rather than in tables with relationships.

---

## MERN Stack Integration

### Key Concepts
- **MERN:** MongoDB, Express.js, React, Node.js.
- **Full-Stack Flow:** Frontend (React) → Backend (Express) → Database (MongoDB).
- **API Integration:** React fetches data from Express endpoints.
- **State Management:** Managing data flow between components.

### Example: MERN Integration
```js
// Backend (Express)
app.get('/api/users', async (req, res) => {
  const users = await User.find();
  res.json(users);
});

// Frontend (React)
function UserList() {
  const [users, setUsers] = useState([]);
  
  useEffect(() => {
    fetch('/api/users')
      .then(res => res.json())
      .then(data => setUsers(data));
  }, []);
  
  return (
    <div>
      {users.map(user => <div key={user._id}>{user.name}</div>)}
    </div>
  );
}
```

### Practice Question
**Q:** How does data flow in a MERN application?

**Solution:**  
1. React frontend makes HTTP requests to Express backend.
2. Express processes requests and interacts with MongoDB.
3. MongoDB returns data to Express.
4. Express sends data back to React as JSON.
5. React updates the UI with the received data.

**Explanation:**  
This creates a complete full-stack application with separation of concerns.

---

## APIs & REST

### Key Concepts
- **API:** Application Programming Interface for communication between systems.
- **REST:** Representational State Transfer, an architectural style for APIs.
- **HTTP Methods:** GET, POST, PUT, DELETE, PATCH.
- **Status Codes:** 200 (OK), 201 (Created), 400 (Bad Request), 404 (Not Found), 500 (Server Error).
- **JSON:** Data format for API communication.

### Example: RESTful API
```js
// GET /api/users - Get all users
app.get('/api/users', async (req, res) => {
  const users = await User.find();
  res.json(users);
});

// POST /api/users - Create user
app.post('/api/users', async (req, res) => {
  const user = new User(req.body);
  await user.save();
  res.status(201).json(user);
});

// PUT /api/users/:id - Update user
app.put('/api/users/:id', async (req, res) => {
  const user = await User.findByIdAndUpdate(req.params.id, req.body);
  res.json(user);
});

// DELETE /api/users/:id - Delete user
app.delete('/api/users/:id', async (req, res) => {
  await User.findByIdAndDelete(req.params.id);
  res.status(204).send();
});
```

### Practice Question
**Q:** What are the main HTTP methods in REST APIs?

**Solution:**  
- GET: Retrieve data
- POST: Create new data
- PUT: Update existing data (full update)
- PATCH: Update existing data (partial update)
- DELETE: Remove data

**Explanation:**  
Each method has a specific purpose in CRUD operations.

---

## Authentication & Security

### Key Concepts
- **Sessions:** Server-side storage of user authentication state.
- **JWT (JSON Web Tokens):** Stateless authentication tokens.
- **Password Hashing:** bcrypt for secure password storage.
- **OAuth:** Third-party authentication (Google, Facebook, etc.).
- **CORS:** Cross-Origin Resource Sharing for security.
- **Input Validation:** Sanitize user inputs to prevent attacks.

### Example: JWT Authentication
```js
const jwt = require('jsonwebtoken');
const bcrypt = require('bcrypt');

// Login
app.post('/login', async (req, res) => {
  const user = await User.findOne({ email: req.body.email });
  if (user && await bcrypt.compare(req.body.password, user.password)) {
    const token = jwt.sign({ userId: user._id }, 'secret_key');
    res.json({ token });
  } else {
    res.status(401).json({ error: 'Invalid credentials' });
  }
});

// Protected route
app.get('/protected', authenticateToken, (req, res) => {
  res.json({ message: 'Access granted' });
});

function authenticateToken(req, res, next) {
  const token = req.headers['authorization'];
  if (!token) return res.sendStatus(401);
  
  jwt.verify(token, 'secret_key', (err, user) => {
    if (err) return res.sendStatus(403);
    req.user = user;
    next();
  });
}
```

### Practice Question
**Q:** Why should passwords be hashed instead of stored in plain text?

**Solution:**  
Hashing provides security by converting passwords into irreversible strings, protecting user data even if the database is compromised.

**Explanation:**  
If a database breach occurs, hashed passwords cannot be reversed to reveal the original passwords.

---

## Deployment

### Key Concepts
- **Hosting Platforms:** Heroku, Vercel, Netlify, AWS, DigitalOcean.
- **Environment Variables:** Store sensitive configuration data.
- **Process Managers:** PM2 for Node.js applications.
- **CI/CD:** Continuous Integration/Continuous Deployment.
- **Domain & SSL:** Custom domains with HTTPS.

### Example: Environment Variables
```js
// .env file
PORT=3000
MONGODB_URI=mongodb://localhost:27017/myapp
JWT_SECRET=mysecretkey

// app.js
require('dotenv').config();
const port = process.env.PORT || 3000;
const mongoUri = process.env.MONGODB_URI;
```

### Example: PM2 Configuration
```json
{
  "name": "my-app",
  "script": "app.js",
  "instances": "max",
  "env": {
    "NODE_ENV": "production"
  }
}
```

### Practice Question
**Q:** What are environment variables and why are they important?

**Solution:**  
Environment variables are configuration values stored outside the application code, used for sensitive data like API keys, database URLs, and environment-specific settings.

**Explanation:**  
They keep sensitive information out of version control and allow different configurations for development, testing, and production environments.

---

## Enhanced EJS & MVC Practical Examples

### Advanced EJS Features
```ejs
<!-- Layout with partials -->
<%- include('header') %>
<main>
  <% users.forEach(user => { %>
    <div class="user-card">
      <h3><%= user.name %></h3>
      <p><%= user.email %></p>
      <% if (user.isAdmin) { %>
        <span class="admin-badge">Admin</span>
      <% } %>
    </div>
  <% }); %>
</main>
<%- include('footer') %>
```

### MVC Implementation
```js
// Model (models/User.js)
const mongoose = require('mongoose');
const userSchema = new mongoose.Schema({
  name: String,
  email: String,
  isAdmin: Boolean
});
module.exports = mongoose.model('User', userSchema);

// Controller (controllers/userController.js)
const User = require('../models/User');

exports.getAllUsers = async (req, res) => {
  try {
    const users = await User.find();
    res.render('users', { users });
  } catch (error) {
    res.status(500).send('Server error');
  }
};

// View (views/users.ejs)
<h1>Users</h1>
<% users.forEach(user => { %>
  <p><%= user.name %> - <%= user.email %></p>
<% }); %>
```

### Practice Question
**Q:** How does MVC architecture improve code organization?

**Solution:**  
MVC separates concerns: Models handle data and business logic, Views handle presentation, and Controllers handle user input and coordinate between Models and Views.

**Explanation:**  
This separation makes code more maintainable, testable, and easier to understand.

---

## Frontend Frameworks (React - Intro)

### Key Concepts & Theory

**React Fundamentals:**
- **Virtual DOM:** A lightweight copy of the actual DOM that React uses for diffing and efficient updates. When state changes, React compares the Virtual DOM with the real DOM and updates only what's necessary.
- **JSX (JavaScript XML):** A syntax extension that allows you to write HTML-like code in JavaScript. JSX gets compiled to `React.createElement()` calls.
- **Components:** Reusable, self-contained pieces of UI that can be either functional (using hooks) or class-based.
- **Props (Properties):** Read-only data passed from parent to child components. Props are immutable and help maintain unidirectional data flow.
- **State:** Mutable data that belongs to a component and can change over time. State changes trigger re-renders.
- **Unidirectional Data Flow:** Data flows down from parent to child components through props, and events flow up through callbacks.

**Component Lifecycle (Class Components):**
- **Mounting:** `constructor()` → `render()` → `componentDidMount()`
- **Updating:** `render()` → `componentDidUpdate()`
- **Unmounting:** `componentWillUnmount()`

**Hooks (Functional Components):**
- **useState:** Manages local state in functional components
- **useEffect:** Handles side effects (API calls, subscriptions, DOM manipulation)
- **useContext:** Consumes React context
- **useReducer:** Manages complex state logic

### Example: React Component with Hooks
```jsx
import React, { useState, useEffect } from 'react';

function UserProfile({ userId }) {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetchUser(userId);
  }, [userId]);

  const fetchUser = async (id) => {
    try {
      const response = await fetch(`/api/users/${id}`);
      const userData = await response.json();
      setUser(userData);
    } catch (error) {
      console.error('Error fetching user:', error);
    } finally {
      setLoading(false);
    }
  };

  if (loading) return <div>Loading...</div>;
  if (!user) return <div>User not found</div>;

  return (
    <div className="user-profile">
      <h2>{user.name}</h2>
      <p>{user.email}</p>
    </div>
  );
}
```

### Practice Question
**Q:** Explain the difference between props and state in React.

**Solution:**  
- **Props:** Immutable data passed from parent to child, used for configuration and data flow down the component tree.
- **State:** Mutable data managed within a component, triggers re-renders when changed, used for component-specific data.

**Explanation:**  
Props create a unidirectional data flow, while state allows components to manage their own data. Props are read-only, but state can be updated using setter functions.

---

## Advanced JavaScript (Expanded)

### ES6+ Features (Detailed)

**Destructuring:**
```js
// Array destructuring
const [first, second, ...rest] = [1, 2, 3, 4, 5];
console.log(first); // 1
console.log(rest); // [3, 4, 5]

// Object destructuring
const { name, age, ...otherProps } = { name: 'Alice', age: 25, city: 'NYC' };
console.log(name); // 'Alice'
console.log(otherProps); // { city: 'NYC' }

// Function parameter destructuring
function greet({ name, age }) {
  return `Hello ${name}, you are ${age} years old`;
}
```

**Spread/Rest Operator:**
```js
// Spread operator (expanding)
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5]; // [1, 2, 3, 4, 5]

const obj1 = { name: 'Alice' };
const obj2 = { ...obj1, age: 25 }; // { name: 'Alice', age: 25 }

// Rest operator (collecting)
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}
```

**Template Literals:**
```js
const name = 'Alice';
const age = 25;
const message = `Hello ${name}, you are ${age} years old`;
const multiLine = `
  This is a
  multi-line
  string
`;
```

**Arrow Functions:**
```js
// Regular function
function add(a, b) {
  return a + b;
}

// Arrow function
const add = (a, b) => a + b;

// Arrow function with block
const multiply = (a, b) => {
  const result = a * b;
  return result;
};
```

**Classes:**
```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    return `Hello, my name is ${this.name}`;
  }

  static create(name, age) {
    return new Person(name, age);
  }
}

class Student extends Person {
  constructor(name, age, grade) {
    super(name, age);
    this.grade = grade;
  }
}
```

### Prototypes and Inheritance (Theory)

**Prototype Chain:**
- Every JavaScript object has a prototype object
- When you access a property, JavaScript looks up the prototype chain
- `Object.prototype` is at the top of the chain
- `__proto__` (deprecated) or `Object.getPrototypeOf()` to access prototype

**Constructor Functions:**
```js
function Person(name) {
  this.name = name;
}

Person.prototype.greet = function() {
  return `Hello, ${this.name}`;
};

const person = new Person('Alice');
console.log(person.greet()); // "Hello, Alice"
```

**Modern Inheritance with Classes:**
```js
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    return `${this.name} makes a sound`;
  }
}

class Dog extends Animal {
  speak() {
    return `${this.name} barks`;
  }
}
```

### Error Handling (Detailed)

**Try-Catch Blocks:**
```js
try {
  const result = riskyOperation();
  console.log(result);
} catch (error) {
  console.error('Error occurred:', error.message);
} finally {
  console.log('This always runs');
}
```

**Custom Errors:**
```js
class ValidationError extends Error {
  constructor(message, field) {
    super(message);
    this.name = 'ValidationError';
    this.field = field;
  }
}

function validateUser(user) {
  if (!user.name) {
    throw new ValidationError('Name is required', 'name');
  }
  if (!user.email) {
    throw new ValidationError('Email is required', 'email');
  }
}
```

**Promise Error Handling:**
```js
fetch('/api/data')
  .then(response => {
    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }
    return response.json();
  })
  .catch(error => {
    console.error('Fetch error:', error);
  });
```

### Modules (ES6 Modules)

**Export/Import:**
```js
// math.js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;
export default class Calculator {
  multiply(a, b) { return a * b; }
}

// main.js
import Calculator, { add, subtract } from './math.js';
import * as math from './math.js';
```

### Practice Question
**Q:** Explain the difference between `==` and `===` in JavaScript with examples.

**Solution:**  
- `==` performs type coercion before comparison
- `===` performs strict equality comparison (no type coercion)

**Examples:**
```js
5 == "5"    // true (string "5" is coerced to number 5)
5 === "5"   // false (different types)

null == undefined  // true
null === undefined // false

0 == false  // true (false is coerced to 0)
0 === false // false
```

**Explanation:**  
Always use `===` for equality comparisons to avoid unexpected type coercion behavior.

---

## Enhanced Theory Concepts

### JavaScript Event Loop (Theory)

**How JavaScript Handles Asynchronous Operations:**
1. **Call Stack:** Where function calls are executed
2. **Web APIs:** Browser APIs for async operations (setTimeout, fetch, etc.)
3. **Callback Queue:** Where completed async operations wait
4. **Event Loop:** Continuously checks if call stack is empty, then moves callbacks from queue to stack

**Example:**
```js
console.log('1');
setTimeout(() => console.log('2'), 0);
console.log('3');
// Output: 1, 3, 2
```

### Memory Management (Theory)

**Garbage Collection:**
- JavaScript automatically manages memory
- Objects no longer referenced are garbage collected
- Memory leaks can occur with closures holding references

**Example of Memory Leak:**
```js
function createLeak() {
  const largeData = new Array(1000000);
  return function() {
    console.log(largeData.length); // largeData is never garbage collected
  };
}
```

### CSS Box Model (Detailed Theory)

**Box Model Components:**
- **Content:** The actual content of the element
- **Padding:** Space between content and border
- **Border:** The border around the element
- **Margin:** Space outside the border

**Box Sizing:**
```css
/* content-box (default) */
.element {
  box-sizing: content-box;
  width: 100px; /* Total width = 100px + padding + border */
}

/* border-box */
.element {
  box-sizing: border-box;
  width: 100px; /* Total width = 100px (includes padding and border) */
}
```

### HTTP Protocol (Theory)

**HTTP Methods:**
- **GET:** Retrieve data (idempotent, safe)
- **POST:** Create new data (not idempotent, not safe)
- **PUT:** Update entire resource (idempotent, not safe)
- **PATCH:** Update partial resource (not idempotent, not safe)
- **DELETE:** Remove resource (idempotent, not safe)

**HTTP Status Codes:**
- **2xx Success:** 200 (OK), 201 (Created), 204 (No Content)
- **3xx Redirection:** 301 (Moved Permanently), 302 (Found)
- **4xx Client Error:** 400 (Bad Request), 401 (Unauthorized), 404 (Not Found)
- **5xx Server Error:** 500 (Internal Server Error), 502 (Bad Gateway)

### Database Normalization (Theory)

**Normal Forms:**
- **1NF:** Each column contains atomic values, no repeating groups
- **2NF:** 1NF + no partial dependencies
- **3NF:** 2NF + no transitive dependencies

**Example:**
```sql
-- Not normalized
Users(id, name, email, phone1, phone2, phone3)

-- Normalized
Users(id, name, email)
UserPhones(user_id, phone_number, phone_type)
```

### Practice Question
**Q:** Explain the concept of "hoisting" in JavaScript with examples.

**Solution:**  
Hoisting is JavaScript's behavior of moving declarations to the top of their scope during the compilation phase.

**Examples:**
```js
console.log(x); // undefined (not ReferenceError)
var x = 5;

// Function declarations are hoisted
sayHello(); // "Hello!"
function sayHello() {
  console.log("Hello!");
}

// Function expressions are not hoisted
sayGoodbye(); // TypeError: sayGoodbye is not a function
var sayGoodbye = function() {
  console.log("Goodbye!");
};
```

**Explanation:**  
Only declarations are hoisted, not initializations. `let` and `const` are hoisted but not initialized (temporal dead zone).

---

## Advanced Web Development Theory

### Web Performance Optimization (Theory)

**Critical Rendering Path:**
1. **Parse HTML:** Build DOM tree
2. **Parse CSS:** Build CSSOM tree
3. **Combine:** Create render tree
4. **Layout:** Calculate positions and sizes
5. **Paint:** Fill pixels on screen

**Performance Metrics:**
- **First Contentful Paint (FCP):** When first content appears
- **Largest Contentful Paint (LCP):** When largest content is visible
- **First Input Delay (FID):** Time to respond to first interaction
- **Cumulative Layout Shift (CLS):** Visual stability measure

**Optimization Techniques:**
```js
// Lazy loading images
<img src="image.jpg" loading="lazy" alt="Description">

// Code splitting
const LazyComponent = React.lazy(() => import('./LazyComponent'));

// Service Worker for caching
if ('serviceWorker' in navigator) {
  navigator.serviceWorker.register('/sw.js');
}
```

### Design Patterns in Web Development

**Module Pattern:**
```js
const Calculator = (function() {
  let privateVariable = 0;
  
  function privateMethod() {
    return privateVariable;
  }
  
  return {
    add: function(x) {
      privateVariable += x;
      return this;
    },
    getValue: function() {
      return privateMethod();
    }
  };
})();
```

**Observer Pattern:**
```js
class EventEmitter {
  constructor() {
    this.events = {};
  }
  
  on(event, callback) {
    if (!this.events[event]) {
      this.events[event] = [];
    }
    this.events[event].push(callback);
  }
  
  emit(event, data) {
    if (this.events[event]) {
      this.events[event].forEach(callback => callback(data));
    }
  }
}
```

**Factory Pattern:**
```js
class UserFactory {
  createUser(type, data) {
    switch(type) {
      case 'admin':
        return new AdminUser(data);
      case 'regular':
        return new RegularUser(data);
      default:
        throw new Error('Invalid user type');
    }
  }
}
```

### Security Best Practices (Theory)

**Cross-Site Scripting (XSS) Prevention:**
```js
// Sanitize user input
function sanitizeInput(input) {
  return input.replace(/[<>]/g, '');
}

// Use Content Security Policy
// In HTML: <meta http-equiv="Content-Security-Policy" content="default-src 'self'">
```

**Cross-Site Request Forgery (CSRF) Protection:**
```js
// Generate CSRF tokens
app.use((req, res, next) => {
  res.locals.csrfToken = generateToken();
  next();
});

// Validate tokens in forms
<form method="POST">
  <input type="hidden" name="_csrf" value="<%= csrfToken %>">
</form>
```

**SQL Injection Prevention:**
```js
// Use parameterized queries
const query = 'SELECT * FROM users WHERE id = ?';
db.query(query, [userId], (err, results) => {
  // Safe from SQL injection
});
```

### Progressive Web Apps (PWA) Theory

**PWA Characteristics:**
- **Progressive:** Work for every user regardless of browser choice
- **Responsive:** Fit any form factor
- **Connectivity Independent:** Enhanced with service workers
- **App-like:** Feel like native apps
- **Fresh:** Always up-to-date via service worker updates
- **Safe:** Served via HTTPS
- **Discoverable:** Identifiable as applications
- **Re-engageable:** Push notifications
- **Installable:** Can be added to home screen
- **Linkable:** Shareable via URLs

**Service Worker Lifecycle:**
```js
// Register service worker
if ('serviceWorker' in navigator) {
  navigator.serviceWorker.register('/sw.js')
    .then(registration => {
      console.log('SW registered');
    })
    .catch(error => {
      console.log('SW registration failed');
    });
}

// Service worker file (sw.js)
self.addEventListener('install', event => {
  event.waitUntil(
    caches.open('v1').then(cache => {
      return cache.addAll([
        '/',
        '/styles/main.css',
        '/scripts/main.js'
      ]);
    })
  );
});

self.addEventListener('fetch', event => {
  event.respondWith(
    caches.match(event.request).then(response => {
      return response || fetch(event.request);
    })
  );
});
```

### Microservices Architecture (Theory)

**Microservices Principles:**
- **Single Responsibility:** Each service has one business capability
- **Autonomy:** Services can be developed, deployed, and scaled independently
- **Resilience:** Services can fail without bringing down the entire system
- **Observability:** Services provide monitoring and logging

**API Gateway Pattern:**
```js
// Express API Gateway
const express = require('express');
const { createProxyMiddleware } = require('http-proxy-middleware');

const app = express();

// Route to user service
app.use('/api/users', createProxyMiddleware({
  target: 'http://user-service:3001',
  changeOrigin: true
}));

// Route to product service
app.use('/api/products', createProxyMiddleware({
  target: 'http://product-service:3002',
  changeOrigin: true
}));
```

**Circuit Breaker Pattern:**
```js
class CircuitBreaker {
  constructor(failureThreshold = 5, timeout = 60000) {
    this.failureThreshold = failureThreshold;
    this.timeout = timeout;
    this.failures = 0;
    this.state = 'CLOSED';
    this.lastFailureTime = null;
  }

  async call(serviceFunction) {
    if (this.state === 'OPEN') {
      if (Date.now() - this.lastFailureTime > this.timeout) {
        this.state = 'HALF_OPEN';
      } else {
        throw new Error('Circuit breaker is OPEN');
      }
    }

    try {
      const result = await serviceFunction();
      this.onSuccess();
      return result;
    } catch (error) {
      this.onFailure();
      throw error;
    }
  }

  onSuccess() {
    this.failures = 0;
    this.state = 'CLOSED';
  }

  onFailure() {
    this.failures++;
    this.lastFailureTime = Date.now();
    if (this.failures >= this.failureThreshold) {
      this.state = 'OPEN';
    }
  }
}
```

### State Management Patterns

**Redux Pattern:**
```js
// Action
const addTodo = (text) => ({
  type: 'ADD_TODO',
  payload: { text, completed: false }
});

// Reducer
const todoReducer = (state = [], action) => {
  switch (action.type) {
    case 'ADD_TODO':
      return [...state, action.payload];
    case 'TOGGLE_TODO':
      return state.map(todo =>
        todo.id === action.payload.id
          ? { ...todo, completed: !todo.completed }
          : todo
      );
    default:
      return state;
  }
};

// Store
const store = createStore(todoReducer);
```

**Context API Pattern:**
```jsx
const ThemeContext = React.createContext();

function ThemeProvider({ children }) {
  const [theme, setTheme] = useState('light');

  const toggleTheme = () => {
    setTheme(prev => prev === 'light' ? 'dark' : 'light');
  };

  return (
    <ThemeContext.Provider value={{ theme, toggleTheme }}>
      {children}
    </ThemeContext.Provider>
  );
}

function useTheme() {
  const context = useContext(ThemeContext);
  if (!context) {
    throw new Error('useTheme must be used within ThemeProvider');
  }
  return context;
}
```

### Testing Strategies (Theory)

**Testing Pyramid:**
- **Unit Tests:** Test individual functions/components (70%)
- **Integration Tests:** Test interactions between components (20%)
- **E2E Tests:** Test complete user workflows (10%)

**Unit Testing Example:**
```js
// Jest test
describe('Calculator', () => {
  test('adds two numbers correctly', () => {
    expect(add(2, 3)).toBe(5);
  });

  test('handles negative numbers', () => {
    expect(add(-1, 1)).toBe(0);
  });
});
```

**Integration Testing Example:**
```js
// Supertest for API testing
const request = require('supertest');
const app = require('../app');

describe('User API', () => {
  test('GET /api/users returns users', async () => {
    const response = await request(app)
      .get('/api/users')
      .expect(200);
    
    expect(response.body).toHaveProperty('users');
    expect(Array.isArray(response.body.users)).toBe(true);
  });
});
```

### Web Accessibility (A11y) Theory

**WCAG Guidelines:**
- **Perceivable:** Information must be presentable to users in ways they can perceive
- **Operable:** User interface components must be operable
- **Understandable:** Information and operation of user interface must be understandable
- **Robust:** Content must be robust enough to be interpreted by assistive technologies

**Accessibility Implementation:**
```jsx
// Semantic HTML
<button aria-label="Close dialog" onClick={closeDialog}>
  <span aria-hidden="true">&times;</span>
</button>

// Keyboard navigation
function handleKeyDown(event) {
  if (event.key === 'Enter' || event.key === ' ') {
    event.preventDefault();
    handleClick();
  }
}

// Focus management
useEffect(() => {
  const firstInput = document.querySelector('input');
  if (firstInput) {
    firstInput.focus();
  }
}, []);
```

### Web APIs and Browser Capabilities

**Web APIs Overview:**
- **Fetch API:** Modern way to make HTTP requests
- **Web Storage:** localStorage and sessionStorage
- **Geolocation API:** Access user's location
- **Web Workers:** Run scripts in background threads
- **WebSockets:** Real-time bidirectional communication
- **WebRTC:** Real-time communication between browsers

**Web Worker Example:**
```js
// Main thread
const worker = new Worker('worker.js');
worker.postMessage({ data: [1, 2, 3, 4, 5] });
worker.onmessage = function(e) {
  console.log('Result:', e.data);
};

// worker.js
self.onmessage = function(e) {
  const result = e.data.data.reduce((sum, num) => sum + num, 0);
  self.postMessage(result);
};
```

**WebSocket Example:**
```js
const socket = new WebSocket('ws://localhost:8080');

socket.onopen = function(event) {
  console.log('Connected to server');
  socket.send('Hello server!');
};

socket.onmessage = function(event) {
  console.log('Message from server:', event.data);
};

socket.onclose = function(event) {
  console.log('Disconnected from server');
};
```

### Practice Question
**Q:** Explain the concept of "event delegation" in JavaScript and provide an example.

**Solution:**  
Event delegation is a technique where you attach an event listener to a parent element instead of multiple child elements, using event bubbling to handle events from child elements.

**Example:**
```js
// Instead of attaching listeners to each button
document.querySelectorAll('.btn').forEach(btn => {
  btn.addEventListener('click', handleClick);
});

// Use event delegation
document.getElementById('container').addEventListener('click', function(e) {
  if (e.target.classList.contains('btn')) {
    handleClick(e);
  }
});
```

**Explanation:**  
Event delegation improves performance by reducing the number of event listeners and works with dynamically added elements.

---

This completes the comprehensive web technologies cheatsheet! The README.md now includes all major topics from HTML basics to MERN stack deployment, with conceptual explanations, code snippets, and practice questions with solutions. 