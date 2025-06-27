# Modern Web Concepts Theory Cheatsheet

A concise guide to modern web development concepts for theory exams. Focuses on best practices, tools, and essential knowledge for today's web.

---

## Table of Contents
- [Responsive Design](#responsive-design)
- [Deployment & Hosting](#deployment--hosting)
- [Version Control (Git)](#version-control-git)
- [Frontend Frameworks (React Basics)](#frontend-frameworks-react-basics)
- [State Management](#state-management)
- [Web Accessibility (A11y)](#web-accessibility-a11y)
- [Web Performance](#web-performance)
- [Other Key Concepts](#other-key-concepts)

---

## Responsive Design
- Designing web pages to look and work well on all devices (desktop, tablet, mobile).
- Uses flexible layouts, media queries, and responsive images.

**Key Techniques:**
- CSS Flexbox & Grid
- Media queries (`@media`)
- Relative units (`em`, `rem`, `%`, `vw`, `vh`)
- Mobile-first design

**Example:**
```css
.container {
  display: flex;
  flex-wrap: wrap;
}
@media (max-width: 600px) {
  .container {
    flex-direction: column;
  }
}
```

## Deployment & Hosting
- Making your web app available on the internet.
- Common platforms: Vercel, Netlify, Heroku, AWS, DigitalOcean.
- Use environment variables for secrets/configuration.
- Set up custom domains and HTTPS.

**CI/CD:**
- Continuous Integration/Continuous Deployment automates testing and deployment.

## Version Control (Git)
- Tracks changes in code, enables collaboration, and manages project history.
- **Repository:** Project folder tracked by Git.
- **Commit:** Snapshot of changes.
- **Branch:** Parallel version for features/experiments.
- **Merge:** Combine changes from branches.

**Common Commands:**
```bash
git init                # Initialize repo
git clone <url>         # Copy repo
git status              # Check changes
git add .               # Stage changes
git commit -m "msg"     # Save snapshot
git branch              # List branches
git checkout -b feature # New branch
git merge feature       # Merge branch
git pull                # Update from remote
git push                # Upload to remote
```

## Frontend Frameworks (React Basics)
- **React:** Library for building user interfaces with components.
- **Component:** Reusable piece of UI (function or class).
- **JSX:** HTML-like syntax in JavaScript.
- **Props:** Data passed to components.
- **State:** Local, changeable data in a component.
- **Hooks:** Functions for state and lifecycle in functional components (`useState`, `useEffect`).

**Example:**
```jsx
import React, { useState } from 'react';
function Counter() {
  const [count, setCount] = useState(0);
  return (
    <button onClick={() => setCount(count + 1)}>
      Count: {count}
    </button>
  );
}
```

## State Management
- Managing and sharing data between components.
- **Local state:** `useState` in React.
- **Global state:** Context API, Redux, MobX, Zustand, etc.

**Redux Example:**
```js
const addTodo = text => ({ type: 'ADD_TODO', payload: text });
function todoReducer(state = [], action) {
  switch (action.type) {
    case 'ADD_TODO':
      return [...state, action.payload];
    default:
      return state;
  }
}
```

## Web Accessibility (A11y)
- Making web apps usable by everyone, including people with disabilities.
- **WCAG:** Web Content Accessibility Guidelines.
- Use semantic HTML (`<button>`, `<nav>`, `<header>`, etc.).
- Provide alt text for images.
- Ensure keyboard navigation.
- Use ARIA attributes for assistive tech.

**Example:**
```jsx
<button aria-label="Close dialog" onClick={closeDialog}>
  <span aria-hidden="true">&times;</span>
</button>
```

## Web Performance
- Fast load times and smooth interactions improve user experience and SEO.
- **Core Web Vitals:** FCP, LCP, FID, CLS.
- Optimize images, minify code, lazy load resources, use caching.

**Example:**
```js
// Lazy loading images
<img src="image.jpg" loading="lazy" alt="Description" />
```

## Other Key Concepts
- **API:** Interface for communication between systems (REST, GraphQL).
- **Testing:** Unit, integration, and E2E tests (Jest, Mocha, Cypress).
- **Security:** XSS, CSRF, input validation, HTTPS.
- **Progressive Web Apps (PWA):** Installable, offline-capable web apps.
- **DevTools:** Browser tools for debugging and performance analysis.

---

This cheatsheet covers the most important modern web concepts for exams. Focus on understanding responsive design, deployment, Git, React, state management, accessibility, and performance! 