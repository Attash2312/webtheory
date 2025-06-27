# JavaScript Core Concepts & Client-Side Cheatsheet

A comprehensive guide to JavaScript fundamentals, client-side development, DOM manipulation, and modern JavaScript features.

---

## Table of Contents
- [JavaScript Core Concepts \& Client-Side Cheatsheet](#javascript-core-concepts--client-side-cheatsheet)
  - [Table of Contents](#table-of-contents)
  - [JavaScript Core Concepts](#javascript-core-concepts)
    - [Variables \& Data Types](#variables--data-types)
    - [Operators](#operators)
    - [Control Flow](#control-flow)
    - [Functions](#functions)
    - [Objects \& Arrays](#objects--arrays)
    - [ES6+ Features](#es6-features)
    - [Error Handling](#error-handling)
  - [Client-Side JavaScript](#client-side-javascript)
    - [DOM Manipulation](#dom-manipulation)
    - [Events](#events)
    - [AJAX \& Fetch API](#ajax--fetch-api)
    - [Local Storage](#local-storage)
    - [Web APIs](#web-apis)
  - [Advanced Concepts](#advanced-concepts)
    - [Closures](#closures)
    - [Promises \& Async/Await](#promises--asyncawait)
    - [Modules](#modules)
    - [Classes](#classes)
  - [Best Practices](#best-practices)
  - [Common Patterns](#common-patterns)

---

## JavaScript Core Concepts

### Variables & Data Types

**Variable Declaration:**
```js
// Modern way (ES6+)
let variable = "value";        // Block-scoped, can be reassigned
const constant = "value";      // Block-scoped, cannot be reassigned
var oldWay = "value";         // Function-scoped (avoid in modern JS)

// Destructuring
const [first, second] = [1, 2];
const { name, age } = { name: "John", age: 30 };
```

**Data Types:**
```js
// Primitive Types
let string = "Hello World";
let number = 42;
let boolean = true;
let nullValue = null;
let undefinedValue = undefined;
let symbol = Symbol("description");
let bigInt = 9007199254740991n;

// Reference Types
let object = { key: "value" };
let array = [1, 2, 3];
let function = () => {};

// Type checking
typeof "string"        // "string"
typeof 42             // "number"
typeof true           // "boolean"
typeof null           // "object" (JavaScript bug)
typeof undefined      // "undefined"
typeof {}             // "object"
typeof []             // "object"
typeof function(){}   // "function"

// Better type checking
Array.isArray([])     // true
Object.prototype.toString.call(null) // "[object Null]"
```

### Operators

**Arithmetic Operators:**
```js
let a = 10, b = 3;

a + b;    // 13 (addition)
a - b;    // 7 (subtraction)
a * b;    // 30 (multiplication)
a / b;    // 3.333... (division)
a % b;    // 1 (modulus)
a ** b;   // 1000 (exponentiation)
a++;      // 11 (increment)
b--;      // 2 (decrement)
```

**Comparison Operators:**
```js
// Equality
5 == "5"     // true (loose equality)
5 === "5"    // false (strict equality)
5 != "5"     // false
5 !== "5"    // true

// Relational
5 > 3        // true
5 >= 5       // true
5 < 10       // true
5 <= 5       // true
```

**Logical Operators:**
```js
// AND, OR, NOT
true && false    // false
true || false    // true
!true            // false

// Short-circuit evaluation
let result = false && someFunction();  // someFunction() not called
let default = user.name || "Anonymous"; // fallback value
```

**Assignment Operators:**
```js
let x = 5;
x += 3;     // x = x + 3
x -= 2;     // x = x - 2
x *= 4;     // x = x * 4
x /= 2;     // x = x / 2
x %= 3;     // x = x % 3
x **= 2;    // x = x ** 2
```

### Control Flow

**Conditional Statements:**
```js
// if...else
if (condition) {
    // code
} else if (anotherCondition) {
    // code
} else {
    // code
}

// Ternary operator
let result = condition ? "yes" : "no";

// Switch statement
switch (value) {
    case 1:
        console.log("One");
        break;
    case 2:
        console.log("Two");
        break;
    default:
        console.log("Default");
}
```

**Loops:**
```js
// for loop
for (let i = 0; i < 5; i++) {
    console.log(i);
}

// for...of (iterables)
for (let item of array) {
    console.log(item);
}

// for...in (object properties)
for (let key in object) {
    console.log(key, object[key]);
}

// while loop
while (condition) {
    // code
}

// do...while loop
do {
    // code
} while (condition);

// Array methods
array.forEach(item => console.log(item));
array.map(item => item * 2);
array.filter(item => item > 5);
array.reduce((acc, item) => acc + item, 0);
```

### Functions

**Function Declaration:**
```js
// Function declaration
function greet(name) {
    return `Hello, ${name}!`;
}

// Function expression
const greet = function(name) {
    return `Hello, ${name}!`;
};

// Arrow function
const greet = (name) => `Hello, ${name}!`;

// Arrow function with block
const greet = (name) => {
    const message = `Hello, ${name}!`;
    return message;
};
```

**Function Parameters:**
```js
// Default parameters
function greet(name = "Anonymous") {
    return `Hello, ${name}!`;
}

// Rest parameters
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}

// Destructuring parameters
function processUser({ name, age, email }) {
    console.log(`${name} is ${age} years old`);
}
```

**Higher-Order Functions:**
```js
// Function that returns a function
function multiply(x) {
    return function(y) {
        return x * y;
    };
}

const multiplyByTwo = multiply(2);
console.log(multiplyByTwo(5)); // 10

// Function that takes a function as parameter
function processArray(array, callback) {
    return array.map(callback);
}

const numbers = [1, 2, 3, 4];
const doubled = processArray(numbers, x => x * 2);
```

### Objects & Arrays

**Object Literals:**
```js
const person = {
    name: "John",
    age: 30,
    greet() {
        return `Hello, I'm ${this.name}`;
    }
};

// Property access
person.name;           // dot notation
person["age"];         // bracket notation
person.greet();        // method call

// Object destructuring
const { name, age } = person;
const { name: personName } = person; // rename

// Spread operator
const updatedPerson = { ...person, age: 31 };
```

**Array Methods:**
```js
const numbers = [1, 2, 3, 4, 5];

// Adding/removing elements
numbers.push(6);           // add to end
numbers.pop();             // remove from end
numbers.unshift(0);        // add to beginning
numbers.shift();           // remove from beginning
numbers.splice(2, 1);      // remove at index

// Finding elements
numbers.indexOf(3);        // 2
numbers.includes(3);       // true
numbers.find(x => x > 3);  // 4
numbers.findIndex(x => x > 3); // 3

// Transforming arrays
numbers.map(x => x * 2);   // [2, 4, 6, 8, 10]
numbers.filter(x => x > 2); // [3, 4, 5]
numbers.reduce((sum, x) => sum + x, 0); // 15

// Sorting
numbers.sort((a, b) => a - b); // ascending
numbers.sort((a, b) => b - a); // descending
```

### ES6+ Features

**Template Literals:**
```js
const name = "John";
const age = 30;
const message = `Hello, my name is ${name} and I'm ${age} years old`;

// Multi-line strings
const html = `
    <div>
        <h1>${name}</h1>
        <p>Age: ${age}</p>
    </div>
`;
```

**Destructuring:**
```js
// Array destructuring
const [first, second, ...rest] = [1, 2, 3, 4, 5];
console.log(first); // 1
console.log(rest);  // [3, 4, 5]

// Object destructuring
const { title, author, ...otherProps } = {
    title: "Book",
    author: "Author",
    year: 2023,
    genre: "Fiction"
};

// Function parameter destructuring
function processUser({ name, age, email = "default@email.com" }) {
    console.log(`${name} is ${age} years old`);
}
```

**Spread & Rest:**
```js
// Spread operator
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5]; // [1, 2, 3, 4, 5]

const obj1 = { name: "John" };
const obj2 = { ...obj1, age: 30 }; // { name: "John", age: 30 }

// Rest operator
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}
```

### Error Handling

**Try-Catch Blocks:**
```js
try {
    // Risky code
    const result = riskyOperation();
    console.log(result);
} catch (error) {
    // Handle error
    console.error("Error occurred:", error.message);
} finally {
    // Always executes
    console.log("Cleanup code");
}
```

**Custom Errors:**
```js
class ValidationError extends Error {
    constructor(message, field) {
        super(message);
        this.name = "ValidationError";
        this.field = field;
    }
}

function validateUser(user) {
    if (!user.name) {
        throw new ValidationError("Name is required", "name");
    }
    if (!user.email) {
        throw new ValidationError("Email is required", "email");
    }
}
```

---

## Client-Side JavaScript

### DOM Manipulation

**Selecting Elements:**
```js
// Single element
const element = document.getElementById("myId");
const element = document.querySelector(".myClass");
const element = document.querySelector("[data-testid='myElement']");

// Multiple elements
const elements = document.getElementsByClassName("myClass");
const elements = document.getElementsByTagName("div");
const elements = document.querySelectorAll(".myClass");
```

**Creating Elements:**
```js
// Create element
const div = document.createElement("div");
div.textContent = "Hello World";
div.className = "my-class";
div.id = "my-id";

// Add to DOM
document.body.appendChild(div);
document.body.insertBefore(div, referenceElement);
document.body.replaceChild(newElement, oldElement);
```

**Modifying Elements:**
```js
const element = document.getElementById("myElement");

// Content
element.textContent = "New text";
element.innerHTML = "<span>HTML content</span>";
element.innerText = "Visible text only";

// Attributes
element.setAttribute("class", "new-class");
element.getAttribute("data-id");
element.removeAttribute("class");
element.hasAttribute("required");

// Classes
element.classList.add("new-class");
element.classList.remove("old-class");
element.classList.toggle("active");
element.classList.contains("active");

// Styles
element.style.backgroundColor = "red";
element.style.cssText = "color: blue; font-size: 16px;";
```

**Traversing DOM:**
```js
const element = document.getElementById("myElement");

// Parent
element.parentElement;
element.parentNode;

// Children
element.children;           // HTMLCollection
element.childNodes;         // NodeList (includes text nodes)
element.firstElementChild;
element.lastElementChild;

// Siblings
element.nextElementSibling;
element.previousElementSibling;
element.nextSibling;
element.previousSibling;
```

### Events

**Event Listeners:**
```js
const button = document.getElementById("myButton");

// Add event listener
button.addEventListener("click", function(event) {
    console.log("Button clicked!");
});

// Remove event listener
const handler = (event) => console.log("Clicked");
button.addEventListener("click", handler);
button.removeEventListener("click", handler);

// Event object
button.addEventListener("click", function(event) {
    event.preventDefault();     // Prevent default behavior
    event.stopPropagation();    // Stop event bubbling
    console.log(event.target);  // Element that triggered event
    console.log(event.currentTarget); // Element with listener
});
```

**Common Events:**
```js
// Mouse events
element.addEventListener("click", handler);
element.addEventListener("dblclick", handler);
element.addEventListener("mousedown", handler);
element.addEventListener("mouseup", handler);
element.addEventListener("mousemove", handler);
element.addEventListener("mouseenter", handler);
element.addEventListener("mouseleave", handler);

// Keyboard events
element.addEventListener("keydown", handler);
element.addEventListener("keyup", handler);
element.addEventListener("keypress", handler);

// Form events
element.addEventListener("submit", handler);
element.addEventListener("change", handler);
element.addEventListener("input", handler);
element.addEventListener("focus", handler);
element.addEventListener("blur", handler);

// Document events
document.addEventListener("DOMContentLoaded", handler);
window.addEventListener("load", handler);
window.addEventListener("resize", handler);
window.addEventListener("scroll", handler);
```

**Event Delegation:**
```js
// Instead of adding listeners to each button
document.querySelectorAll(".btn").forEach(btn => {
    btn.addEventListener("click", handleClick);
});

// Use event delegation
document.getElementById("container").addEventListener("click", function(event) {
    if (event.target.classList.contains("btn")) {
        handleClick(event);
    }
});
```

### AJAX & Fetch API

**Fetch API:**
```js
// Basic GET request
fetch("https://api.example.com/data")
    .then(response => {
        if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
        }
        return response.json();
    })
    .then(data => console.log(data))
    .catch(error => console.error("Error:", error));

// POST request
fetch("https://api.example.com/users", {
    method: "POST",
    headers: {
        "Content-Type": "application/json",
    },
    body: JSON.stringify({
        name: "John",
        email: "john@example.com"
    })
})
.then(response => response.json())
.then(data => console.log(data));

// Async/await version
async function fetchData() {
    try {
        const response = await fetch("https://api.example.com/data");
        if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
        }
        const data = await response.json();
        return data;
    } catch (error) {
        console.error("Error:", error);
    }
}
```

**XMLHttpRequest (Legacy):**
```js
const xhr = new XMLHttpRequest();
xhr.open("GET", "https://api.example.com/data", true);

xhr.onreadystatechange = function() {
    if (xhr.readyState === 4 && xhr.status === 200) {
        const data = JSON.parse(xhr.responseText);
        console.log(data);
    }
};

xhr.send();
```

### Local Storage

**Web Storage API:**
```js
// localStorage (persistent)
localStorage.setItem("user", JSON.stringify({ name: "John", age: 30 }));
const user = JSON.parse(localStorage.getItem("user"));
localStorage.removeItem("user");
localStorage.clear();

// sessionStorage (session-only)
sessionStorage.setItem("token", "abc123");
const token = sessionStorage.getItem("token");
sessionStorage.removeItem("token");

// Storage event (when storage changes in other tabs)
window.addEventListener("storage", function(event) {
    console.log("Storage changed:", event.key, event.newValue);
});
```

**Cookies:**
```js
// Set cookie
document.cookie = "name=John; expires=Fri, 31 Dec 2023 23:59:59 GMT; path=/";

// Get cookie
function getCookie(name) {
    const value = `; ${document.cookie}`;
    const parts = value.split(`; ${name}=`);
    if (parts.length === 2) return parts.pop().split(';').shift();
}

// Delete cookie
document.cookie = "name=; expires=Thu, 01 Jan 1970 00:00:00 GMT; path=/";
```

### Web APIs

**Geolocation:**
```js
if ("geolocation" in navigator) {
    navigator.geolocation.getCurrentPosition(
        function(position) {
            console.log("Latitude:", position.coords.latitude);
            console.log("Longitude:", position.coords.longitude);
        },
        function(error) {
            console.error("Error:", error.message);
        }
    );
}
```

**Web Workers:**
```js
// Main thread
const worker = new Worker("worker.js");
worker.postMessage({ data: [1, 2, 3, 4, 5] });

worker.onmessage = function(event) {
    console.log("Result:", event.data);
};

worker.onerror = function(error) {
    console.error("Worker error:", error);
};

// worker.js
self.onmessage = function(event) {
    const result = event.data.data.reduce((sum, num) => sum + num, 0);
    self.postMessage(result);
};
```

**WebSockets:**
```js
const socket = new WebSocket("ws://localhost:8080");

socket.onopen = function(event) {
    console.log("Connected to server");
    socket.send("Hello server!");
};

socket.onmessage = function(event) {
    console.log("Message from server:", event.data);
};

socket.onclose = function(event) {
    console.log("Disconnected from server");
};

socket.onerror = function(error) {
    console.error("WebSocket error:", error);
};
```

---

## Advanced Concepts

### Closures

**Basic Closure:**
```js
function outerFunction(x) {
    return function innerFunction(y) {
        return x + y; // x is captured from outer scope
    };
}

const addFive = outerFunction(5);
console.log(addFive(3)); // 8
```

**Practical Closure Examples:**
```js
// Counter with closure
function createCounter() {
    let count = 0;
    return {
        increment: () => ++count,
        decrement: () => --count,
        getCount: () => count
    };
}

const counter = createCounter();
console.log(counter.increment()); // 1
console.log(counter.increment()); // 2
console.log(counter.getCount());  // 2

// Data privacy
function createWallet(initialBalance) {
    let balance = initialBalance;
    
    return {
        getBalance: () => balance,
        deposit: (amount) => {
            if (amount > 0) {
                balance += amount;
                return true;
            }
            return false;
        },
        withdraw: (amount) => {
            if (amount > 0 && amount <= balance) {
                balance -= amount;
                return true;
            }
            return false;
        }
    };
}
```

### Promises & Async/Await

**Creating Promises:**
```js
// Promise constructor
const myPromise = new Promise((resolve, reject) => {
    // Async operation
    setTimeout(() => {
        const success = Math.random() > 0.5;
        if (success) {
            resolve("Success!");
        } else {
            reject("Failed!");
        }
    }, 1000);
});

// Using promises
myPromise
    .then(result => console.log(result))
    .catch(error => console.error(error))
    .finally(() => console.log("Always executes"));
```

**Promise Methods:**
```js
// Promise.all (all must succeed)
Promise.all([
    fetch("/api/users"),
    fetch("/api/posts"),
    fetch("/api/comments")
])
.then(responses => Promise.all(responses.map(r => r.json())))
.then(([users, posts, comments]) => {
    console.log(users, posts, comments);
});

// Promise.race (first to complete)
Promise.race([
    fetch("/api/data"),
    new Promise((_, reject) => setTimeout(() => reject("Timeout"), 5000))
])
.then(response => response.json())
.catch(error => console.error(error));

// Promise.allSettled (all complete, regardless of success/failure)
Promise.allSettled([
    Promise.resolve(1),
    Promise.reject("error"),
    Promise.resolve(3)
])
.then(results => {
    results.forEach(result => {
        if (result.status === "fulfilled") {
            console.log("Success:", result.value);
        } else {
            console.log("Error:", result.reason);
        }
    });
});
```

**Async/Await:**
```js
async function fetchUserData(userId) {
    try {
        const response = await fetch(`/api/users/${userId}`);
        if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
        }
        const user = await response.json();
        
        const postsResponse = await fetch(`/api/users/${userId}/posts`);
        const posts = await postsResponse.json();
        
        return { user, posts };
    } catch (error) {
        console.error("Error fetching user data:", error);
        throw error;
    }
}

// Using async function
fetchUserData(123)
    .then(data => console.log(data))
    .catch(error => console.error(error));
```

### Modules

**ES6 Modules:**
```js
// math.js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;
export const multiply = (a, b) => a * b;

export default class Calculator {
    constructor() {
        this.history = [];
    }
    
    calculate(operation, a, b) {
        const result = operation(a, b);
        this.history.push({ operation: operation.name, a, b, result });
        return result;
    }
}

// main.js
import Calculator, { add, subtract, multiply } from "./math.js";
import * as math from "./math.js";

const calc = new Calculator();
console.log(calc.calculate(add, 5, 3)); // 8
console.log(math.multiply(4, 2)); // 8
```

**Dynamic Imports:**
```js
// Lazy loading
async function loadModule() {
    const module = await import("./heavy-module.js");
    module.doSomething();
}

// Conditional loading
if (condition) {
    const { feature } = await import("./feature.js");
    feature();
}
```

### Classes

**Class Declaration:**
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
    
    get info() {
        return `${this.name} is ${this.age} years old`;
    }
    
    set info(value) {
        [this.name, this.age] = value.split(" ");
    }
}

class Student extends Person {
    constructor(name, age, grade) {
        super(name, age);
        this.grade = grade;
    }
    
    study() {
        return `${this.name} is studying`;
    }
    
    greet() {
        return `${super.greet()} and I'm a student`;
    }
}
```

**Private Fields (ES2022):**
```js
class BankAccount {
    #balance = 0; // private field
    
    constructor(initialBalance) {
        this.#balance = initialBalance;
    }
    
    deposit(amount) {
        if (amount > 0) {
            this.#balance += amount;
            return true;
        }
        return false;
    }
    
    getBalance() {
        return this.#balance;
    }
}
```

---

## Best Practices

**Code Organization:**
```js
// Use meaningful variable names
const userAge = 25;           // Good
const ua = 25;               // Bad

// Use const by default, let when needed
const PI = 3.14159;
let counter = 0;

// Use template literals for string concatenation
const message = `Hello ${name}, you are ${age} years old`;

// Use arrow functions for short functions
const add = (a, b) => a + b;

// Use destructuring for cleaner code
const { name, age, email } = user;
```

**Error Handling:**
```js
// Always handle promises
fetch("/api/data")
    .then(response => response.json())
    .catch(error => {
        console.error("Fetch failed:", error);
        // Provide fallback or user feedback
    });

// Use try-catch for synchronous operations
try {
    const result = JSON.parse(invalidJson);
} catch (error) {
    console.error("JSON parsing failed:", error);
    // Handle gracefully
}
```

**Performance:**
```js
// Debounce function calls
function debounce(func, wait) {
    let timeout;
    return function executedFunction(...args) {
        const later = () => {
            clearTimeout(timeout);
            func(...args);
        };
        clearTimeout(timeout);
        timeout = setTimeout(later, wait);
    };
}

// Throttle function calls
function throttle(func, limit) {
    let inThrottle;
    return function() {
        const args = arguments;
        const context = this;
        if (!inThrottle) {
            func.apply(context, args);
            inThrottle = true;
            setTimeout(() => inThrottle = false, limit);
        }
    };
}
```

---

## Common Patterns

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
    
    off(event, callback) {
        if (this.events[event]) {
            this.events[event] = this.events[event].filter(cb => cb !== callback);
        }
    }
}
```

**Singleton Pattern:**
```js
class Database {
    constructor() {
        if (Database.instance) {
            return Database.instance;
        }
        Database.instance = this;
        this.connection = "Connected to database";
    }
    
    query(sql) {
        return `Executing: ${sql}`;
    }
}

const db1 = new Database();
const db2 = new Database();
console.log(db1 === db2); // true
```

**Factory Pattern:**
```js
class UserFactory {
    createUser(type, data) {
        switch(type) {
            case "admin":
                return new AdminUser(data);
            case "regular":
                return new RegularUser(data);
            default:
                throw new Error("Invalid user type");
        }
    }
}

class AdminUser {
    constructor(data) {
        this.name = data.name;
        this.role = "admin";
        this.permissions = ["read", "write", "delete"];
    }
}

class RegularUser {
    constructor(data) {
        this.name = data.name;
        this.role = "user";
        this.permissions = ["read"];
    }
}
```

---

This JavaScript cheatsheet covers the essential concepts for both core JavaScript and client-side development. Use it as a quick reference for syntax, patterns, and best practices! 