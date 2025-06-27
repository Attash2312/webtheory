# Express.js Theory Cheatsheet

A comprehensive guide to Express.js concepts for theory exams. Focuses on middleware, controllers, models, routing, and Express architecture patterns.

---

## Table of Contents
- [What is Express.js?](#what-is-expressjs)
- [Express.js Architecture](#expressjs-architecture)
- [Middleware](#middleware)
- [Controllers](#controllers)
- [Models](#models)
- [Routes & Routing](#routes--routing)
- [Error Handling](#error-handling)
- [Express.js Best Practices](#expressjs-best-practices)

---

## What is Express.js?
- **Express.js** is a minimal and flexible Node.js web application framework.
- Provides a robust set of features for web and mobile applications.
- Simplifies the development of web applications and APIs.
- Built on top of Node.js HTTP module.

## Express.js Architecture
- **Request-Response Cycle:** Client sends request → Express processes → Response sent back.
- **Middleware Stack:** Functions that execute in sequence during request processing.
- **Modular Design:** Separate concerns into routes, controllers, models, and middleware.

**Basic Structure:**
```
Request → Middleware → Route → Controller → Model → Database
                ↓
Response ← Middleware ← Route ← Controller ← Model ← Database
```

## Middleware
- **Middleware** are functions that have access to the request object (req), response object (res), and the next middleware function in the application's request-response cycle.
- Execute in the order they are defined.
- Can modify request/response objects, end the request-response cycle, or call the next middleware.

**Types of Middleware:**
1. **Application-level middleware:** Bound to the app object using `app.use()`.
2. **Router-level middleware:** Bound to a specific router using `router.use()`.
3. **Error-handling middleware:** Takes four arguments (err, req, res, next).
4. **Built-in middleware:** Express.static, express.json, express.urlencoded.
5. **Third-party middleware:** cors, helmet, morgan, etc.

**Example:**
```js
// Application-level middleware
app.use(express.json());
app.use(express.static('public'));

// Custom middleware
app.use((req, res, next) => {
  console.log(`${req.method} ${req.url}`);
  next();
});

// Error-handling middleware
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send('Something broke!');
});
```

## Controllers
- **Controllers** handle the business logic of your application.
- Receive requests from routes, interact with models, and send responses.
- Should be thin and focused on a single responsibility.
- Can be organized by feature or resource.

**Controller Structure:**
```js
// controllers/userController.js
const User = require('../models/User');

exports.getAllUsers = async (req, res) => {
  try {
    const users = await User.find();
    res.json(users);
  } catch (error) {
    res.status(500).json({ error: error.message });
  }
};

exports.createUser = async (req, res) => {
  try {
    const user = new User(req.body);
    await user.save();
    res.status(201).json(user);
  } catch (error) {
    res.status(400).json({ error: error.message });
  }
};
```

**Controller Best Practices:**
- Keep controllers thin (business logic in services/models).
- Use async/await for database operations.
- Handle errors consistently.
- Return appropriate HTTP status codes.
- Validate input data.

## Models
- **Models** represent data structures and business logic.
- In Express with Mongoose, models define schemas and provide database interaction methods.
- Handle data validation, relationships, and business rules.

**Model Structure:**
```js
// models/User.js
const mongoose = require('mongoose');

const userSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true,
    trim: true
  },
  email: {
    type: String,
    required: true,
    unique: true,
    lowercase: true
  },
  age: {
    type: Number,
    min: 0,
    max: 120
  },
  createdAt: {
    type: Date,
    default: Date.now
  }
});

// Instance methods
userSchema.methods.getFullName = function() {
  return `${this.name} (${this.email})`;
};

// Static methods
userSchema.statics.findByEmail = function(email) {
  return this.findOne({ email: email });
};

module.exports = mongoose.model('User', userSchema);
```

**Model Features:**
- **Schema Definition:** Structure and validation rules.
- **Validation:** Built-in and custom validators.
- **Methods:** Instance and static methods.
- **Virtuals:** Computed properties.
- **Middleware:** Pre/post hooks for operations.

## Routes & Routing
- **Routes** define endpoints and map HTTP methods to controller functions.
- Organize routes by feature or resource.
- Can be modularized using Express Router.

**Route Structure:**
```js
// routes/userRoutes.js
const express = require('express');
const router = express.Router();
const userController = require('../controllers/userController');

// GET /users
router.get('/', userController.getAllUsers);

// POST /users
router.post('/', userController.createUser);

// GET /users/:id
router.get('/:id', userController.getUserById);

module.exports = router;
```

**Route Parameters:**
```js
// Access route parameters
router.get('/users/:id', (req, res) => {
  const userId = req.params.id;
  // Use userId to fetch user
});
```

## Error Handling
- **Synchronous Errors:** Use try-catch blocks.
- **Asynchronous Errors:** Use async/await with try-catch or pass errors to next().
- **Global Error Handler:** Catch all unhandled errors.

**Error Handling Patterns:**
```js
// Async error handling
app.get('/users', async (req, res, next) => {
  try {
    const users = await User.find();
    res.json(users);
  } catch (error) {
    next(error); // Pass to error handler
  }
});

// Global error handler
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(err.status || 500).json({
    error: err.message || 'Internal Server Error'
  });
});
```

## Express.js Best Practices
- **Project Structure:** Organize by features or layers.
- **Environment Configuration:** Use environment variables.
- **Security:** Use helmet, cors, rate limiting.
- **Validation:** Validate input data (express-validator).
- **Logging:** Use morgan or winston for logging.
- **Testing:** Write unit and integration tests.

**Project Structure Example:**
```
project/
├── controllers/
│   ├── userController.js
│   └── postController.js
├── models/
│   ├── User.js
│   └── Post.js
├── routes/
│   ├── userRoutes.js
│   └── postRoutes.js
├── middleware/
│   ├── auth.js
│   └── validation.js
├── config/
│   └── database.js
├── app.js
└── package.json
```

---

This cheatsheet covers the most important Express.js theory for exams. Focus on understanding middleware, controllers, models, routing, and Express architecture patterns! 