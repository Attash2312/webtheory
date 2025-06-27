# Keywords and Packages Explained

A quick reference for every keyword, method, and package used in the examples across all cheatsheets. Use this to look up any unfamiliar term or package.

---

## HTML
| Name         | Type     | Description                                              | Example Usage                |
|--------------|----------|----------------------------------------------------------|------------------------------|
| `<html>`     | Tag      | Root element of an HTML document.                        | `<html lang="en">`         |
| `<head>`     | Tag      | Contains meta-information about the document.            | `<head>...</head>`           |
| `<body>`     | Tag      | Contains the content of the document.                    | `<body>...</body>`           |
| `<header>`   | Tag      | Represents introductory content or navigation links.      | `<header>...</header>`       |
| `<nav>`      | Tag      | Contains navigation links.                               | `<nav>...</nav>`             |
| `<main>`     | Tag      | Main content of the document.                            | `<main>...</main>`           |
| `<section>`  | Tag      | Defines a section in a document.                         | `<section>...</section>`     |
| `<footer>`   | Tag      | Footer for the document or section.                      | `<footer>...</footer>`       |
| `<form>`     | Tag      | Used to collect user input.                              | `<form>...</form>`           |
| `<input>`    | Tag      | Input field for user data.                               | `<input type="text">`      |
| `<button>`   | Tag      | Clickable button.                                        | `<button>Submit</button>`    |
| `alt`        | Attribute| Alternative text for images (accessibility).             | `<img alt="desc">`         |
| `aria-*`     | Attribute| Accessibility attributes for assistive technologies.     | `<div aria-label="menu">`  |

---

## CSS
| Name         | Type     | Description                                              | Example Usage                |
|--------------|----------|----------------------------------------------------------|------------------------------|
| `selector`   | Concept  | Pattern to select HTML elements.                         | `.class`, `#id`, `div`       |
| `box model`  | Concept  | Layout model: content, padding, border, margin.          | `box-sizing: border-box;`    |
| `flexbox`    | Layout   | Flexible box layout for arranging items.                 | `display: flex;`             |
| `grid`       | Layout   | 2D layout system for web pages.                          | `display: grid;`             |
| `media query`| Feature  | CSS technique for responsive design.                     | `@media (max-width: 600px)`  |
| `px`, `em`, `rem`, `%` | Unit | Units for sizing elements.                        | `font-size: 2em;`            |
| `:hover`     | Pseudo-class | Style when mouse is over an element.                | `a:hover { color: red; }`    |
| `::before`   | Pseudo-element | Insert content before element.                   | `p::before { ... }`          |

---

## JavaScript
| Name         | Type     | Description                                              | Example Usage                |
|--------------|----------|----------------------------------------------------------|------------------------------|
| `let`        | Keyword  | Declares a block-scoped variable.                        | `let x = 5;`                 |
| `const`      | Keyword  | Declares a block-scoped, constant variable.              | `const PI = 3.14;`           |
| `var`        | Keyword  | Declares a function-scoped variable (legacy).            | `var y = 10;`                |
| `function`   | Keyword  | Declares a function.                                     | `function foo() {}`          |
| `=>`         | Syntax   | Arrow function syntax.                                   | `const add = (a,b)=>a+b;`    |
| `if`, `else` | Keyword  | Conditional statements.                                  | `if (x > 0) {...}`           |
| `switch`     | Keyword  | Multi-branch conditional.                                | `switch(x) {...}`            |
| `for`, `while`, `do...while` | Keyword | Looping constructs.                  | `for (let i=0;i<5;i++)`      |
| `return`     | Keyword  | Returns a value from a function.                         | `return x + y;`              |
| `Promise`    | Object   | Represents an async operation.                           | `new Promise(...)`           |
| `async/await`| Syntax   | Syntactic sugar for Promises.                            | `async function foo(){}`     |
| `document`   | Object   | Represents the HTML document.                            | `document.getElementById()`  |
| `addEventListener` | Method | Attaches an event handler.                          | `el.addEventListener(...)`   |
| `console.log`| Method   | Prints to the browser console.                           | `console.log('Hi')`          |
| `Array.isArray` | Method | Checks if value is an array.                            | `Array.isArray([])`          |
| `map`, `filter`, `reduce`, `forEach` | Method | Array iteration methods.      | `arr.map(x=>x*2)`            |
| `getElementById()` | Method | Gets element by ID.                              | `document.getElementById('myId')` |
| `getElementsByClassName()` | Method | Gets elements by class.                    | `document.getElementsByClassName('myClass')` |
| `querySelector()` | Method | Gets first element matching CSS selector.        | `document.querySelector('.myClass')` |
| `querySelectorAll()` | Method | Gets all elements matching CSS selector.      | `document.querySelectorAll('p')` |
| `innerHTML`  | Property | Gets/sets HTML content of element.                      | `el.innerHTML = '<p>New content</p>'` |
| `textContent`| Property | Gets/sets text content of element.                      | `el.textContent = 'New text'` |
| `setAttribute()` | Method | Sets attribute on element.                        | `el.setAttribute('class', 'newClass')` |
| `getAttribute()` | Method | Gets attribute value from element.                | `el.getAttribute('href')` |
| `createElement()` | Method | Creates new HTML element.                        | `document.createElement('div')` |
| `appendChild()` | Method | Adds child element to parent.                      | `parent.appendChild(child)` |
| `removeChild()` | Method | Removes child element from parent.                  | `parent.removeChild(child)` |
| `fetch()`    | Method   | Makes HTTP requests (modern AJAX).                     | `fetch('/api/data').then(...)` |
| `XMLHttpRequest` | Class | Legacy way to make HTTP requests.                | `new XMLHttpRequest()` |
| `localStorage` | Object | Browser storage for persistent data.               | `localStorage.setItem('key', 'value')` |
| `sessionStorage` | Object | Browser storage for session data.               | `sessionStorage.setItem('key', 'value')` |
| `JSON.parse()` | Method | Converts JSON string to object.                   | `JSON.parse('{"name":"John"}')` |
| `JSON.stringify()` | Method | Converts object to JSON string.                 | `JSON.stringify({name: 'John'})` |
| `setTimeout()` | Method | Executes function after delay.                    | `setTimeout(()=>{}, 1000)` |
| `setInterval()` | Method | Repeatedly executes function.                     | `setInterval(()=>{}, 1000)` |
| `clearTimeout()` | Method | Cancels setTimeout.                              | `clearTimeout(timeoutId)` |
| `clearInterval()` | Method | Cancels setInterval.                             | `clearInterval(intervalId)` |
| `Math.random()` | Method | Generates random number (0-1).                   | `Math.random()` |
| `Math.floor()` | Method | Rounds down to nearest integer.                   | `Math.floor(3.7)` |
| `Date`       | Class    | Handles dates and times.                              | `new Date()` |
| `RegExp`     | Class    | Regular expressions for pattern matching.               | `new RegExp('pattern')` |
| `try/catch`  | Statement | Error handling block.                               | `try {...} catch(err) {...}` |
| `throw`      | Statement | Throws custom error.                                 | `throw new Error('message')` |

**🔍 Important JavaScript Concepts:**

**DOM Manipulation:** JavaScript can change HTML elements, attributes, and CSS styles dynamically. Think of it as having a remote control for your webpage.

**Event Handling:** JavaScript responds to user actions (clicks, form submissions, etc.) by executing functions. Like having sensors that trigger actions.

**Asynchronous Programming:** JavaScript can perform tasks in the background (like loading data) without freezing the webpage. Like cooking while doing other chores.

---

## Node.js
| Name         | Type     | Description                                              | Example Usage                |
|--------------|----------|----------------------------------------------------------|------------------------------|
| `require()`  | Function | Imports modules in Node.js.                              | `const fs = require('fs');`  |
| `module.exports` | Object | Exports from a module.                              | `module.exports = { foo };`  |
| `__dirname`  | Variable | Current directory path.                                  | `console.log(__dirname);`   |
| `__filename` | Variable | Current file path.                                       | `console.log(__filename);`  |
| `process`    | Object   | Information about current Node.js process.               | `process.env.PORT`           |
| `Buffer`     | Class    | Handles binary data.                                     | `Buffer.from('Hello')`       |
| `EventEmitter` | Class | Handles custom events.                              | `const events = require('events');` |
| `setTimeout` | Function | Executes code after delay.                               | `setTimeout(()=>{}, 1000);`  |
| `setInterval`| Function | Repeatedly executes code.                                | `setInterval(()=>{}, 1000);` |

**🔍 Important Node.js Concepts:**

**Event Loop:** Node.js uses a single-threaded event loop that handles multiple operations asynchronously. Think of it as a waiter taking orders (non-blocking) while the kitchen cooks (async operations).

**Non-blocking I/O:** Node.js doesn't wait for operations like file reading or database queries to complete before moving to the next task.

---

## Express.js
| Name         | Type     | Description                                              | Example Usage                |
|--------------|----------|----------------------------------------------------------|------------------------------|
| `express()`  | Function | Creates an Express application.                          | `const app = express();`     |
| `app.use()`  | Method   | Mounts middleware function.                              | `app.use(express.json());`   |
| `app.get()`  | Method   | Handles GET requests.                                    | `app.get('/users', handler);`|
| `app.post()` | Method   | Handles POST requests.                                   | `app.post('/users', handler);`|
| `app.put()`  | Method   | Handles PUT requests.                                    | `app.put('/users/:id', handler);`|
| `app.delete()`| Method  | Handles DELETE requests.                                 | `app.delete('/users/:id', handler);`|
| `req`        | Object   | Request object with data from client.                    | `req.body`, `req.params`     |
| `res`        | Object   | Response object to send data back.                       | `res.json()`, `res.send()`   |
| `next`       | Function | Passes control to next middleware.                       | `next();`                    |
| `Router()`   | Class    | Creates modular route handlers.                          | `const router = Router();`   |
| `express.static()` | Function | Serves static files.                              | `app.use(express.static('public'));` |
| `express.json()` | Middleware | Parses JSON request bodies.                        | `app.use(express.json());`   |
| `express.urlencoded()` | Middleware | Parses URL-encoded bodies.                    | `app.use(express.urlencoded());` |

**🔍 Important Express.js Concepts:**

**Middleware:** Functions that run between the request and response. They can modify the request/response objects, end the request-response cycle, or call the next middleware. Think of middleware as checkpoints that every request must pass through.

**Request-Response Cycle:** 
1. Client sends request → 2. Express receives it → 3. Middleware processes it → 4. Route handler responds → 5. Response sent back to client

---

## MongoDB & Mongoose
| Name         | Type     | Description                                              | Example Usage                |
|--------------|----------|----------------------------------------------------------|------------------------------|
| `mongoose`   | Package  | MongoDB object modeling for Node.js.                     | `const mongoose = require('mongoose');` |
| `Schema`     | Class    | Defines document structure and validation.               | `const userSchema = new Schema({...});` |
| `Model`      | Class    | Creates a model from schema.                             | `const User = mongoose.model('User', schema);` |
| `connect()`  | Method   | Connects to MongoDB database.                            | `mongoose.connect('mongodb://localhost/db');` |
| `save()`     | Method   | Saves document to database.                              | `await user.save();`         |
| `find()`     | Method   | Finds documents matching criteria.                       | `await User.find({age: {$gte: 18}});` |
| `findOne()`  | Method   | Finds first document matching criteria.                   | `await User.findOne({email: 'test@test.com'});` |
| `findById()` | Method   | Finds document by ID.                                    | `await User.findById(id);`   |
| `updateOne()`| Method   | Updates first matching document.                         | `await User.updateOne({_id: id}, {name: 'John'});` |
| `deleteOne()`| Method   | Deletes first matching document.                         | `await User.deleteOne({_id: id});` |
| `aggregate()`| Method   | Performs aggregation operations.                         | `await User.aggregate([{$group: {...}}]);` |
| `$gte`, `$lte`, `$in`, `$nin` | Operator | MongoDB comparison operators.        | `{age: {$gte: 18}}`          |
| `$set`, `$push`, `$pull` | Operator | MongoDB update operators.                    | `{$set: {name: 'John'}}`     |

**🔍 Important MongoDB Concepts:**

**Document-Oriented:** MongoDB stores data as JSON-like documents instead of tables. Each document can have different fields, making it flexible for changing data structures.

**Collections:** Similar to tables in SQL, but collections contain documents (not rows). Documents in the same collection can have different structures.

**BSON:** Binary JSON format used by MongoDB for efficient storage and querying.

---

## Other Packages
| Name         | Type     | Description                                              | Example Usage                |
|--------------|----------|----------------------------------------------------------|------------------------------|
| `cors`       | Package  | Enables Cross-Origin Resource Sharing.                   | `app.use(cors());`           |
| `helmet`     | Package  | Security middleware for Express.                         | `app.use(helmet());`         |
| `morgan`     | Package  | HTTP request logger middleware.                          | `app.use(morgan('combined'));` |
| `bcrypt`     | Package  | Password hashing library.                                | `const hash = await bcrypt.hash(password, 10);` |
| `jsonwebtoken` | Package | Creates and verifies JWT tokens.                    | `const token = jwt.sign(payload, secret);` |
| `dotenv`     | Package  | Loads environment variables from .env file.              | `require('dotenv').config();` |
| `multer`     | Package  | Middleware for handling file uploads.                    | `const upload = multer({dest: 'uploads/'});` |
| `nodemailer` | Package  | Sends emails from Node.js.                               | `transporter.sendMail(mailOptions);` |
| `socket.io`  | Package  | Real-time bidirectional communication.                   | `io.on('connection', (socket) => {});` |
| `axios`      | Package  | HTTP client for making requests.                         | `const response = await axios.get(url);` |
| `lodash`     | Package  | Utility library for common operations.                   | `_.map(array, item => item * 2);` |
| `moment`     | Package  | Date manipulation library.                               | `moment().format('YYYY-MM-DD');` |
| `ejs`        | Template Engine | Server-side HTML template engine.                | `app.set('view engine', 'ejs');` |
| `pug`        | Template Engine | Concise HTML template engine.                      | `app.set('view engine', 'pug');` |
| `handlebars` | Template Engine | Logic-less template engine.                        | `app.set('view engine', 'hbs');` |
| `express-session` | Package | Session management for Express.                   | `app.use(session({...}));` |
| `connect-flash` | Package | Flash messages for Express.                        | `app.use(flash());` |
| `express-validator` | Package | Input validation middleware.                    | `const { body } = require('express-validator');` |
| `joi`        | Package  | Schema validation library.                               | `const schema = Joi.object({...});` |
| `nodemon`    | Package  | Automatically restarts server on file changes.           | `nodemon app.js` |
| `pm2`        | Package  | Process manager for Node.js applications.                | `pm2 start app.js` |
| `jest`       | Package  | JavaScript testing framework.                            | `jest test.js` |
| `supertest`  | Package  | HTTP testing library for Express.                       | `request(app).get('/').expect(200)` |

**🔍 Important Package Explanations:**

**CORS (Cross-Origin Resource Sharing):** 
- **What it does:** Allows your frontend (running on one domain) to make requests to your backend (running on another domain)
- **Why needed:** Browsers block requests between different domains for security
- **Real example:** Your React app (localhost:3000) needs to talk to your Express API (localhost:5000)
- **Usage:** `app.use(cors())` - allows all origins, or configure specific origins

**Helmet (Security Middleware):**
- **What it does:** Adds security headers to your Express app to protect against common web vulnerabilities
- **Why needed:** Prevents attacks like XSS (Cross-Site Scripting), clickjacking, and other security issues
- **Real example:** Sets headers like `X-Frame-Options: DENY` to prevent your site from being embedded in iframes
- **Usage:** `app.use(helmet())` - adds multiple security headers automatically

**Morgan (HTTP Request Logger):**
- **What it does:** Logs all HTTP requests to your Express server (method, URL, status code, response time)
- **Why needed:** Helps you debug and monitor your application by seeing what requests are being made
- **Real example:** Logs: `GET /users 200 15.234 ms - 1234` (GET request to /users, status 200, took 15ms, response size 1234 bytes)
- **Usage:** `app.use(morgan('combined'))` - logs in combined format

**EJS (Embedded JavaScript):**
- **What it does:** Template engine that lets you embed JavaScript code inside HTML
- **Why needed:** Creates dynamic HTML pages on the server before sending to browser
- **Real example:** `<h1>Welcome, <%= user.name %>!</h1>` - inserts user's name into HTML
- **Usage:** `app.set('view engine', 'ejs')` and `res.render('page', {data})`

**Express-Session:**
- **What it does:** Manages user sessions (stores user data between requests)
- **Why needed:** Keeps users logged in and stores their preferences/data
- **Real example:** Stores user ID in session so they stay logged in across page visits
- **Usage:** `app.use(session({secret: 'key', resave: false, saveUninitialized: false}))`

**Multer (File Upload):**
- **What it does:** Handles file uploads from HTML forms
- **Why needed:** Processes uploaded files (images, documents, etc.) on the server
- **Real example:** User uploads profile picture, multer saves it to server and gives you file info
- **Usage:** `const upload = multer({dest: 'uploads/'})` and `app.post('/upload', upload.single('file'))`

**Nodemon (Development Tool):**
- **What it does:** Automatically restarts your Node.js server when you save file changes
- **Why needed:** Saves time during development - no need to manually restart server
- **Real example:** You change your Express route, save the file, and server automatically restarts
- **Usage:** `nodemon app.js` instead of `node app.js`

**PM2 (Process Manager):**
- **What it does:** Manages Node.js applications in production (restarts on crashes, load balancing)
- **Why needed:** Keeps your app running 24/7 and handles multiple instances
- **Real example:** Your app crashes, PM2 automatically restarts it and logs the error
- **Usage:** `pm2 start app.js` and `pm2 list` to see running processes

## Applied Scenarios Quick Reference

### Frontend Scenarios
- **Form Validation:** Use JavaScript to validate user input before submission
- **Dynamic Content:** Use DOM manipulation to update page content without reloading
- **Responsive Design:** Use CSS media queries and flexbox/grid for mobile-friendly layouts
- **User Interaction:** Use event listeners to handle clicks, form submissions, etc.

### Backend Scenarios
- **API Development:** Use Express.js to create RESTful endpoints
- **Database Operations:** Use Mongoose to perform CRUD operations on MongoDB
- **Authentication:** Use JWT tokens and bcrypt for secure user login
- **File Uploads:** Use multer to handle file uploads from forms
- **Real-time Features:** Use Socket.io for chat applications or live updates

### Full-Stack Scenarios
- **User Registration/Login:** Frontend form → Backend validation → Database storage → JWT token
- **Data Display:** Backend API → Frontend fetch → DOM manipulation
- **Search Functionality:** Frontend input → Backend query → Database search → Results display
- **Real-time Chat:** Socket.io for instant messaging between users 