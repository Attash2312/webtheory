# Code Templates and Structure Guide

A comprehensive guide showing exactly where each type of code goes in different scenarios. Perfect for applied exam questions and real-world development.

---

## Table of Contents
- [HTML Structure Templates](#html-structure-templates)
- [CSS Organization Patterns](#css-organization-patterns)
- [JavaScript Placement Strategies](#javascript-placement-strategies)
- [Express.js Application Structure](#expressjs-application-structure)
- [MongoDB Integration Patterns](#mongodb-integration-patterns)
- [Full-Stack Application Templates](#full-stack-application-templates)
- [Common Code Patterns](#common-code-patterns)

---

## HTML Structure Templates

### Basic HTML Page Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Meta tags go here -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title</title>
    
    <!-- CSS links go here -->
    <link rel="stylesheet" href="styles.css">
    
    <!-- External libraries (if any) -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
    <!-- Header section -->
    <header>
        <nav>
            <!-- Navigation content -->
        </nav>
    </header>
    
    <!-- Main content -->
    <main>
        <!-- Your main content goes here -->
    </main>
    
    <!-- Footer section -->
    <footer>
        <!-- Footer content -->
    </footer>
    
    <!-- JavaScript goes at the bottom -->
    <script src="script.js"></script>
</body>
</html>
```

### Form Template
```html
<form action="/submit" method="POST" id="myForm">
    <!-- Text input -->
    <div class="form-group">
        <label for="username">Username:</label>
        <input type="text" id="username" name="username" required>
    </div>
    
    <!-- Email input -->
    <div class="form-group">
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>
    </div>
    
    <!-- Password input -->
    <div class="form-group">
        <label for="password">Password:</label>
        <input type="password" id="password" name="password" required>
    </div>
    
    <!-- Select dropdown -->
    <div class="form-group">
        <label for="country">Country:</label>
        <select id="country" name="country">
            <option value="">Select a country</option>
            <option value="us">USA</option>
            <option value="uk">UK</option>
        </select>
    </div>
    
    <!-- Checkbox -->
    <div class="form-group">
        <input type="checkbox" id="agree" name="agree" required>
        <label for="agree">I agree to terms</label>
    </div>
    
    <!-- Radio buttons -->
    <div class="form-group">
        <input type="radio" id="male" name="gender" value="male">
        <label for="male">Male</label>
        <input type="radio" id="female" name="gender" value="female">
        <label for="female">Female</label>
    </div>
    
    <!-- Submit button -->
    <button type="submit">Submit</button>
</form>
```

### Data Display Template
```html
<!-- Table for displaying data -->
<table id="dataTable">
    <thead>
        <tr>
            <th>Name</th>
            <th>Email</th>
            <th>Actions</th>
        </tr>
    </thead>
    <tbody id="tableBody">
        <!-- Data rows will be inserted here by JavaScript -->
    </tbody>
</table>

<!-- Card layout for displaying items -->
<div class="card-container" id="cardContainer">
    <!-- Cards will be inserted here by JavaScript -->
</div>

<!-- List for displaying items -->
<ul id="itemList">
    <!-- List items will be inserted here by JavaScript -->
</ul>
```

---

## CSS Organization Patterns

### CSS File Structure
```css
/* ===== RESET & BASE STYLES ===== */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
}

/* ===== LAYOUT COMPONENTS ===== */
.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

/* ===== NAVIGATION STYLES ===== */
nav {
    background: #333;
    padding: 1rem;
}

nav ul {
    list-style: none;
    display: flex;
    gap: 20px;
}

/* ===== FORM STYLES ===== */
.form-group {
    margin-bottom: 1rem;
}

.form-group label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: bold;
}

.form-group input,
.form-group select,
.form-group textarea {
    width: 100%;
    padding: 0.5rem;
    border: 1px solid #ddd;
    border-radius: 4px;
}

/* ===== BUTTON STYLES ===== */
.btn {
    padding: 0.5rem 1rem;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

.btn-primary {
    background: #007bff;
    color: white;
}

.btn-danger {
    background: #dc3545;
    color: white;
}

/* ===== RESPONSIVE DESIGN ===== */
@media (max-width: 768px) {
    nav ul {
        flex-direction: column;
    }
    
    .container {
        padding: 0 10px;
    }
}
```

### Flexbox Layout Template
```css
/* Flexbox container */
.flex-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 20px;
}

/* Flexbox item */
.flex-item {
    flex: 1 1 300px; /* grow, shrink, basis */
}

/* Centering with flexbox */
.center-container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}
```

### Grid Layout Template
```css
/* Grid container */
.grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
    padding: 20px;
}

/* Grid item */
.grid-item {
    background: #f8f9fa;
    padding: 20px;
    border-radius: 8px;
}
```

---

## JavaScript Placement Strategies

### External JavaScript File (script.js)
```javascript
// ===== DOM CONTENT LOADED =====
document.addEventListener('DOMContentLoaded', function() {
    // All your JavaScript code goes here
    initializeApp();
});

// ===== INITIALIZATION FUNCTION =====
function initializeApp() {
    // Set up event listeners
    setupEventListeners();
    
    // Load initial data
    loadData();
}

// ===== EVENT LISTENERS =====
function setupEventListeners() {
    // Form submission
    const form = document.getElementById('myForm');
    if (form) {
        form.addEventListener('submit', handleFormSubmit);
    }
    
    // Button clicks
    const buttons = document.querySelectorAll('.btn');
    buttons.forEach(button => {
        button.addEventListener('click', handleButtonClick);
    });
}

// ===== FORM HANDLING =====
function handleFormSubmit(event) {
    event.preventDefault();
    
    // Get form data
    const formData = new FormData(event.target);
    const data = Object.fromEntries(formData);
    
    // Validate data
    if (validateForm(data)) {
        // Send data to server
        submitForm(data);
    }
}

// ===== DATA VALIDATION =====
function validateForm(data) {
    const errors = [];
    
    if (!data.username || data.username.length < 3) {
        errors.push('Username must be at least 3 characters');
    }
    
    if (!data.email || !isValidEmail(data.email)) {
        errors.push('Please enter a valid email');
    }
    
    if (errors.length > 0) {
        displayErrors(errors);
        return false;
    }
    
    return true;
}

// ===== API CALLS =====
async function submitForm(data) {
    try {
        const response = await fetch('/api/submit', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
            },
            body: JSON.stringify(data)
        });
        
        if (response.ok) {
            const result = await response.json();
            showSuccess('Form submitted successfully!');
        } else {
            throw new Error('Submission failed');
        }
    } catch (error) {
        showError('Error submitting form: ' + error.message);
    }
}

// ===== DOM MANIPULATION =====
function displayData(data) {
    const container = document.getElementById('dataContainer');
    
    if (Array.isArray(data)) {
        // Display as list
        container.innerHTML = data.map(item => `
            <div class="item">
                <h3>${item.name}</h3>
                <p>${item.description}</p>
            </div>
        `).join('');
    } else {
        // Display single item
        container.innerHTML = `
            <div class="item">
                <h3>${data.name}</h3>
                <p>${data.description}</p>
            </div>
        `;
    }
}

// ===== UTILITY FUNCTIONS =====
function isValidEmail(email) {
    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return emailRegex.test(email);
}

function showSuccess(message) {
    // Display success message
    alert(message); // Replace with better UI
}

function showError(message) {
    // Display error message
    alert('Error: ' + message); // Replace with better UI
}
```

### Inline JavaScript (when needed)
```html
<!-- For simple interactions -->
<button onclick="handleClick()">Click me</button>

<script>
function handleClick() {
    alert('Button clicked!');
}
</script>
```

---

## Express.js Application Structure

### Main Application File (app.js)
```javascript
// ===== IMPORTS =====
const express = require('express');
const mongoose = require('mongoose');
const cors = require('cors');
const helmet = require('helmet');
const morgan = require('morgan');
require('dotenv').config();

// ===== CREATE EXPRESS APP =====
const app = express();
const PORT = process.env.PORT || 3000;

// ===== MIDDLEWARE SETUP =====
app.use(helmet()); // Security headers
app.use(cors()); // Enable CORS
app.use(morgan('combined')); // Logging
app.use(express.json()); // Parse JSON bodies
app.use(express.urlencoded({ extended: true })); // Parse URL-encoded bodies
app.use(express.static('public')); // Serve static files

// ===== DATABASE CONNECTION =====
mongoose.connect(process.env.MONGODB_URI || 'mongodb://localhost:27017/myapp', {
    useNewUrlParser: true,
    useUnifiedTopology: true
})
.then(() => console.log('Connected to MongoDB'))
.catch(err => console.error('MongoDB connection error:', err));

// ===== ROUTE IMPORTS =====
const userRoutes = require('./routes/users');
const productRoutes = require('./routes/products');

// ===== ROUTE SETUP =====
app.use('/api/users', userRoutes);
app.use('/api/products', productRoutes);

// ===== BASIC ROUTES =====
app.get('/', (req, res) => {
    res.send('Welcome to the API');
});

// ===== ERROR HANDLING MIDDLEWARE =====
app.use((err, req, res, next) => {
    console.error(err.stack);
    res.status(500).send('Something broke!');
});

// ===== 404 HANDLER =====
app.use((req, res) => {
    res.status(404).send('Page not found');
});

// ===== START SERVER =====
app.listen(PORT, () => {
    console.log(`Server running on port ${PORT}`);
});
```

### Route File Template (routes/users.js)
```javascript
const express = require('express');
const router = express.Router();
const User = require('../models/User');
const { body, validationResult } = require('express-validator');

// ===== GET ALL USERS =====
router.get('/', async (req, res) => {
    try {
        const users = await User.find();
        res.json(users);
    } catch (error) {
        res.status(500).json({ message: error.message });
    }
});

// ===== GET SINGLE USER =====
router.get('/:id', async (req, res) => {
    try {
        const user = await User.findById(req.params.id);
        if (!user) {
            return res.status(404).json({ message: 'User not found' });
        }
        res.json(user);
    } catch (error) {
        res.status(500).json({ message: error.message });
    }
});

// ===== CREATE USER =====
router.post('/', [
    body('name').notEmpty().withMessage('Name is required'),
    body('email').isEmail().withMessage('Valid email is required'),
    body('password').isLength({ min: 6 }).withMessage('Password must be at least 6 characters')
], async (req, res) => {
    // Check for validation errors
    const errors = validationResult(req);
    if (!errors.isEmpty()) {
        return res.status(400).json({ errors: errors.array() });
    }
    
    try {
        const user = new User(req.body);
        const savedUser = await user.save();
        res.status(201).json(savedUser);
    } catch (error) {
        res.status(400).json({ message: error.message });
    }
});

// ===== UPDATE USER =====
router.put('/:id', async (req, res) => {
    try {
        const user = await User.findByIdAndUpdate(
            req.params.id, 
            req.body, 
            { new: true, runValidators: true }
        );
        if (!user) {
            return res.status(404).json({ message: 'User not found' });
        }
        res.json(user);
    } catch (error) {
        res.status(400).json({ message: error.message });
    }
});

// ===== DELETE USER =====
router.delete('/:id', async (req, res) => {
    try {
        const user = await User.findByIdAndDelete(req.params.id);
        if (!user) {
            return res.status(404).json({ message: 'User not found' });
        }
        res.json({ message: 'User deleted successfully' });
    } catch (error) {
        res.status(500).json({ message: error.message });
    }
});

module.exports = router;
```

### Controller Template (controllers/userController.js)
```javascript
const User = require('../models/User');

// ===== GET ALL USERS =====
exports.getAllUsers = async (req, res) => {
    try {
        const users = await User.find();
        res.json(users);
    } catch (error) {
        res.status(500).json({ message: error.message });
    }
};

// ===== GET USER BY ID =====
exports.getUserById = async (req, res) => {
    try {
        const user = await User.findById(req.params.id);
        if (!user) {
            return res.status(404).json({ message: 'User not found' });
        }
        res.json(user);
    } catch (error) {
        res.status(500).json({ message: error.message });
    }
};

// ===== CREATE USER =====
exports.createUser = async (req, res) => {
    try {
        const user = new User(req.body);
        const savedUser = await user.save();
        res.status(201).json(savedUser);
    } catch (error) {
        res.status(400).json({ message: error.message });
    }
};

// ===== UPDATE USER =====
exports.updateUser = async (req, res) => {
    try {
        const user = await User.findByIdAndUpdate(
            req.params.id, 
            req.body, 
            { new: true, runValidators: true }
        );
        if (!user) {
            return res.status(404).json({ message: 'User not found' });
        }
        res.json(user);
    } catch (error) {
        res.status(400).json({ message: error.message });
    }
};

// ===== DELETE USER =====
exports.deleteUser = async (req, res) => {
    try {
        const user = await User.findByIdAndDelete(req.params.id);
        if (!user) {
            return res.status(404).json({ message: 'User not found' });
        }
        res.json({ message: 'User deleted successfully' });
    } catch (error) {
        res.status(500).json({ message: error.message });
    }
};
```

---

## MongoDB Integration Patterns

### Model Template (models/User.js)
```javascript
const mongoose = require('mongoose');

// ===== SCHEMA DEFINITION =====
const userSchema = new mongoose.Schema({
    name: {
        type: String,
        required: [true, 'Name is required'],
        trim: true,
        minlength: [2, 'Name must be at least 2 characters']
    },
    email: {
        type: String,
        required: [true, 'Email is required'],
        unique: true,
        lowercase: true,
        match: [/^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/, 'Please enter a valid email']
    },
    password: {
        type: String,
        required: [true, 'Password is required'],
        minlength: [6, 'Password must be at least 6 characters']
    },
    age: {
        type: Number,
        min: [0, 'Age cannot be negative'],
        max: [120, 'Age cannot exceed 120']
    },
    isActive: {
        type: Boolean,
        default: true
    },
    createdAt: {
        type: Date,
        default: Date.now
    }
}, {
    timestamps: true // Adds createdAt and updatedAt automatically
});

// ===== INSTANCE METHODS =====
userSchema.methods.getFullName = function() {
    return `${this.name} (${this.email})`;
};

userSchema.methods.isAdult = function() {
    return this.age >= 18;
};

// ===== STATIC METHODS =====
userSchema.statics.findByEmail = function(email) {
    return this.findOne({ email: email });
};

userSchema.statics.findActiveUsers = function() {
    return this.find({ isActive: true });
};

// ===== VIRTUAL PROPERTIES =====
userSchema.virtual('displayName').get(function() {
    return this.name.toUpperCase();
});

// ===== MIDDLEWARE (PRE/POST HOOKS) =====
userSchema.pre('save', function(next) {
    // This runs before saving
    console.log('Saving user:', this.name);
    next();
});

userSchema.post('save', function(doc, next) {
    // This runs after saving
    console.log('User saved:', doc.name);
    next();
});

// ===== INDEXES =====
userSchema.index({ email: 1 });
userSchema.index({ createdAt: -1 });

module.exports = mongoose.model('User', userSchema);
```

### Database Operations Template
```javascript
// ===== CREATE OPERATIONS =====
async function createUser(userData) {
    try {
        const user = new User(userData);
        const savedUser = await user.save();
        return savedUser;
    } catch (error) {
        throw error;
    }
}

// ===== READ OPERATIONS =====
async function getAllUsers() {
    try {
        const users = await User.find();
        return users;
    } catch (error) {
        throw error;
    }
}

async function getUserById(id) {
    try {
        const user = await User.findById(id);
        return user;
    } catch (error) {
        throw error;
    }
}

async function findUsersByCriteria(criteria) {
    try {
        const users = await User.find(criteria);
        return users;
    } catch (error) {
        throw error;
    }
}

// ===== UPDATE OPERATIONS =====
async function updateUser(id, updateData) {
    try {
        const user = await User.findByIdAndUpdate(
            id, 
            updateData, 
            { new: true, runValidators: true }
        );
        return user;
    } catch (error) {
        throw error;
    }
}

// ===== DELETE OPERATIONS =====
async function deleteUser(id) {
    try {
        const user = await User.findByIdAndDelete(id);
        return user;
    } catch (error) {
        throw error;
    }
}

// ===== AGGREGATION OPERATIONS =====
async function getUserStats() {
    try {
        const stats = await User.aggregate([
            {
                $group: {
                    _id: null,
                    totalUsers: { $sum: 1 },
                    avgAge: { $avg: '$age' },
                    activeUsers: {
                        $sum: { $cond: ['$isActive', 1, 0] }
                    }
                }
            }
        ]);
        return stats[0];
    } catch (error) {
        throw error;
    }
}
```

---

## Full-Stack Application Templates

### Complete CRUD Application Structure
```
project/
├── public/
│   ├── index.html
│   ├── styles.css
│   └── script.js
├── views/
│   ├── layouts/
│   │   └── main.ejs
│   └── pages/
│       ├── home.ejs
│       ├── users.ejs
│       └── user-form.ejs
├── routes/
│   ├── index.js
│   └── users.js
├── controllers/
│   └── userController.js
├── models/
│   └── User.js
├── middleware/
│   ├── auth.js
│   └── validation.js
├── config/
│   └── database.js
├── app.js
├── package.json
└── .env
```

### EJS Template with Express (views/users.ejs)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Users List</title>
    <link rel="stylesheet" href="/styles.css">
</head>
<body>
    <div class="container">
        <h1>Users List</h1>
        
        <!-- Add User Button -->
        <a href="/users/new" class="btn btn-primary">Add New User</a>
        
        <!-- Users Table -->
        <table class="users-table">
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Email</th>
                    <th>Age</th>
                    <th>Actions</th>
                </tr>
            </thead>
            <tbody>
                <% users.forEach(user => { %>
                    <tr>
                        <td><%= user.name %></td>
                        <td><%= user.email %></td>
                        <td><%= user.age || 'N/A' %></td>
                        <td>
                            <a href="/users/<%= user._id %>" class="btn btn-small">View</a>
                            <a href="/users/<%= user._id %>/edit" class="btn btn-small">Edit</a>
                            <button onclick="deleteUser('<%= user._id %>')" class="btn btn-small btn-danger">Delete</button>
                        </td>
                    </tr>
                <% }); %>
            </tbody>
        </table>
    </div>
    
    <script>
        async function deleteUser(userId) {
            if (confirm('Are you sure you want to delete this user?')) {
                try {
                    const response = await fetch(`/users/${userId}`, {
                        method: 'DELETE'
                    });
                    
                    if (response.ok) {
                        location.reload();
                    } else {
                        alert('Error deleting user');
                    }
                } catch (error) {
                    alert('Error: ' + error.message);
                }
            }
        }
    </script>
</body>
</html>
```

---

## Common Code Patterns

### Authentication Pattern
```javascript
// Middleware for checking if user is logged in
function requireAuth(req, res, next) {
    if (req.session.userId) {
        next();
    } else {
        res.redirect('/login');
    }
}

// Login route
app.post('/login', async (req, res) => {
    try {
        const { email, password } = req.body;
        const user = await User.findOne({ email });
        
        if (user && await bcrypt.compare(password, user.password)) {
            req.session.userId = user._id;
            res.redirect('/dashboard');
        } else {
            res.render('login', { error: 'Invalid credentials' });
        }
    } catch (error) {
        res.render('login', { error: 'Login failed' });
    }
});
```

### File Upload Pattern
```javascript
const multer = require('multer');
const storage = multer.diskStorage({
    destination: (req, file, cb) => {
        cb(null, 'uploads/');
    },
    filename: (req, file, cb) => {
        cb(null, Date.now() + '-' + file.originalname);
    }
});

const upload = multer({ storage: storage });

app.post('/upload', upload.single('file'), (req, res) => {
    if (req.file) {
        res.json({ 
            message: 'File uploaded successfully',
            filename: req.file.filename 
        });
    } else {
        res.status(400).json({ message: 'No file uploaded' });
    }
});
```

### API Response Pattern
```javascript
// Success response
function sendSuccess(res, data, message = 'Success', status = 200) {
    res.status(status).json({
        success: true,
        message: message,
        data: data
    });
}

// Error response
function sendError(res, message = 'Error occurred', status = 500) {
    res.status(status).json({
        success: false,
        message: message
    });
}

// Usage in routes
app.get('/users', async (req, res) => {
    try {
        const users = await User.find();
        sendSuccess(res, users, 'Users retrieved successfully');
    } catch (error) {
        sendError(res, 'Failed to retrieve users');
    }
});
```

### Form Validation Pattern
```javascript
const { body, validationResult } = require('express-validator');

const validateUser = [
    body('name')
        .notEmpty().withMessage('Name is required')
        .isLength({ min: 2 }).withMessage('Name must be at least 2 characters'),
    body('email')
        .isEmail().withMessage('Valid email is required'),
    body('password')
        .isLength({ min: 6 }).withMessage('Password must be at least 6 characters')
];

app.post('/users', validateUser, (req, res) => {
    const errors = validationResult(req);
    if (!errors.isEmpty()) {
        return res.status(400).json({ errors: errors.array() });
    }
    
    // Process valid data
    // ...
});
```

This template guide shows you exactly where each piece of code goes and how to structure different parts of your applications. Use this as a reference when building applications for your applied exam scenarios! 