# MVC & EJS Theory Cheatsheet

A concise guide to MVC architecture and EJS templating for theory exams. Focuses on concepts, structure, and practical understanding.

---

## Table of Contents
- [What is MVC?](#what-is-mvc)
- [MVC Architecture Explained](#mvc-architecture-explained)
- [Separation of Concerns](#separation-of-concerns)
- [MVC in Express.js](#mvc-in-expressjs)
- [What is EJS?](#what-is-ejs)
- [EJS Templating Features](#ejs-templating-features)
- [Partials & Layouts](#partials--layouts)
- [Passing Data to Views](#passing-data-to-views)
- [Sample Code Snippets](#sample-code-snippets)

---

## What is MVC?
- **MVC** stands for Model-View-Controller.
- It is a software architectural pattern for organizing code in web applications.
- Separates application logic into three interconnected components:
  - **Model:** Manages data and business logic
  - **View:** Handles presentation/UI
  - **Controller:** Handles user input, updates model, and selects view

## MVC Architecture Explained
- **Model:** Represents the data and rules of the application (e.g., database models, validation).
- **View:** Displays data to the user (e.g., HTML templates, EJS files).
- **Controller:** Receives user input, interacts with the model, and renders the appropriate view.

**Diagram:**
```
User <-> Controller <-> Model <-> Database
           |
         View
```

## Separation of Concerns
- Each component has a single responsibility.
- Improves maintainability, scalability, and testability.
- Changes in one part (e.g., UI) do not affect others (e.g., data logic).

## MVC in Express.js
- **Model:** Mongoose schemas/models or plain JS classes/objects.
- **View:** EJS, Pug, or other template engines.
- **Controller:** Express route handlers (functions that process requests).

**Example Structure:**
```
project/
  models/User.js
  controllers/userController.js
  views/users.ejs
  app.js
```

## What is EJS?
- **EJS** stands for Embedded JavaScript.
- A simple templating language that lets you generate HTML markup with plain JavaScript.
- Used as the "View" in MVC with Express.js.

## EJS Templating Features
- Embed JS code in HTML using `<% %>` (logic) and `<%= %>` (output value).
- Supports loops, conditionals, includes, and partials.

**Example:**
```ejs
<ul>
  <% users.forEach(user => { %>
    <li><%= user.name %></li>
  <% }) %>
</ul>
```

## Partials & Layouts
- **Partials:** Reusable EJS files (e.g., header, footer) included in multiple views.
- **Layouts:** Common page structure (not built-in, but can be implemented with includes).

**Example:**
```ejs
<!-- views/partials/header.ejs -->
<header><h1>My App</h1></header>

<!-- views/users.ejs -->
<%- include('partials/header') %>
<ul>
  <% users.forEach(user => { %>
    <li><%= user.name %></li>
  <% }) %>
</ul>
```

## Passing Data to Views
- Use `res.render('view', data)` in Express to pass data to EJS templates.

**Example:**
```js
// Controller
exports.listUsers = async (req, res) => {
  const users = await User.find();
  res.render('users', { users });
};
```

## Sample Code Snippets

**MVC Example in Express:**
```js
// models/User.js
const mongoose = require('mongoose');
const userSchema = new mongoose.Schema({ name: String, email: String });
module.exports = mongoose.model('User', userSchema);

// controllers/userController.js
const User = require('../models/User');
exports.listUsers = async (req, res) => {
  const users = await User.find();
  res.render('users', { users });
};

// views/users.ejs
<ul>
  <% users.forEach(user => { %>
    <li><%= user.name %> - <%= user.email %></li>
  <% }) %>
</ul>
```

---

This cheatsheet covers the most important MVC and EJS theory for exams. Focus on understanding the architecture, separation of concerns, and how data flows from controller to view! 