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

---

## Node.js
// To be filled in next

## Express.js
// To be filled in next

## MongoDB & Mongoose
// To be filled in next

## Other Packages
// To be filled in next 