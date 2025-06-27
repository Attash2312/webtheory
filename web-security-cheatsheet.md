# Web Security & Best Practices Cheatsheet

A concise guide to web security concepts and best practices for theory exams. Focuses on vulnerabilities, prevention, and secure coding principles.

---

## Table of Contents
- [Common Web Vulnerabilities](#common-web-vulnerabilities)
- [Cross-Site Scripting (XSS)](#cross-site-scripting-xss)
- [Cross-Site Request Forgery (CSRF)](#cross-site-request-forgery-csrf)
- [SQL Injection](#sql-injection)
- [Authentication & Authorization](#authentication--authorization)
- [JWT (JSON Web Tokens)](#jwt-json-web-tokens)
- [HTTPS & Secure Communication](#https--secure-communication)
- [Input Validation & Sanitization](#input-validation--sanitization)
- [Environment Variables](#environment-variables)
- [Best Practices](#best-practices)

---

## Common Web Vulnerabilities
- **XSS (Cross-Site Scripting):** Injecting malicious scripts into web pages.
- **CSRF (Cross-Site Request Forgery):** Forcing users to perform unwanted actions.
- **SQL Injection:** Injecting malicious SQL queries via user input.
- **Insecure Authentication:** Weak password storage, session hijacking.
- **Sensitive Data Exposure:** Leaking secrets, API keys, or user data.

## Cross-Site Scripting (XSS)
- Occurs when user input is rendered as HTML/JS without sanitization.
- Allows attackers to execute scripts in users' browsers.

**Prevention:**
- Always escape user input in HTML.
- Use frameworks that auto-escape (e.g., EJS, React).
- Set Content Security Policy (CSP) headers.

**Example:**
```js
function sanitizeInput(input) {
  return input.replace(/[<>]/g, '');
}
```

## Cross-Site Request Forgery (CSRF)
- Tricks users into submitting requests they did not intend (e.g., form submission).

**Prevention:**
- Use CSRF tokens in forms.
- Check `Origin` and `Referer` headers.
- Use `SameSite` cookies.

**Example:**
```js
// Express with csurf middleware
const csrf = require('csurf');
app.use(csrf());
```

## SQL Injection
- Occurs when user input is directly included in SQL queries.
- Allows attackers to manipulate the database.

**Prevention:**
- Use parameterized queries/prepared statements.
- Validate and sanitize all user input.

**Example:**
```js
// Using parameterized queries
const query = 'SELECT * FROM users WHERE id = ?';
db.query(query, [userId], (err, results) => {
  // Safe from SQL injection
});
```

## Authentication & Authorization
- **Authentication:** Verifying user identity (login).
- **Authorization:** Checking user permissions (access control).
- Use strong password hashing (bcrypt).
- Use sessions or JWT for authentication.
- Implement role-based access control (RBAC).

## JWT (JSON Web Tokens)
- Compact, URL-safe tokens for stateless authentication.
- Contains header, payload, and signature.
- Used for API authentication and authorization.

**Example:**
```js
const jwt = require('jsonwebtoken');
const token = jwt.sign({ userId: user._id }, 'secret_key');
// To verify:
jwt.verify(token, 'secret_key');
```

## HTTPS & Secure Communication
- Use HTTPS to encrypt data between client and server.
- Prevents eavesdropping and man-in-the-middle attacks.
- Obtain SSL/TLS certificates from trusted authorities.

## Input Validation & Sanitization
- Validate all user input (type, length, format).
- Sanitize input to remove/escape dangerous characters.
- Use libraries (validator.js, express-validator).

**Example:**
```js
const { body, validationResult } = require('express-validator');
app.post('/register', [
  body('email').isEmail(),
  body('password').isLength({ min: 6 })
], (req, res) => {
  const errors = validationResult(req);
  if (!errors.isEmpty()) {
    return res.status(400).json({ errors: errors.array() });
  }
  // Continue registration
});
```

## Environment Variables
- Store sensitive data (API keys, DB URIs) outside codebase.
- Use `.env` files and `process.env` in Node.js.
- Never commit secrets to version control.

**Example:**
```js
require('dotenv').config();
const dbUri = process.env.MONGODB_URI;
```

## Best Practices
- Use HTTPS everywhere.
- Hash passwords with bcrypt.
- Validate and sanitize all user input.
- Use environment variables for secrets.
- Keep dependencies up to date.
- Limit user permissions (principle of least privilege).
- Regularly audit and test for vulnerabilities.

---

This cheatsheet covers the most important web security theory for exams. Focus on understanding vulnerabilities, prevention, and secure coding practices! 