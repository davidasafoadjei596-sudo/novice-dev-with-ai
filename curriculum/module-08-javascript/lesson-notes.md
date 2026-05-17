# Module 8 — Introduction to JavaScript: Lesson Notes

**Prerequisites:** Module 7 milestone complete
**Read before:** Opening VS Code today

---

## Concept 1 — The Three Layers (Recap)

```
HTML  → WHAT things are    (structure)
CSS   → HOW things look    (appearance)
JS    → WHAT things do     (behaviour)
```

JavaScript reads your HTML, listens for what the user does (clicks, typing, scrolling), and changes the page in response. It does NOT directly control appearance — it adds and removes CSS classes, which then control appearance.

---

## Concept 2 — Linking JavaScript

```html
<!-- Always at the BOTTOM of <body>, or use defer in <head> -->
<body>
  <!-- your HTML content -->
  <script src="script.js" defer></script>
</body>
```

**Why `defer`?** It tells the browser: "Download this file but don't run it until the HTML is fully loaded." Without it, JS runs before the HTML exists and can't find elements.

---

## Concept 3 — The Browser Console

Open DevTools → Console tab. This is your JS playground and error log.

```javascript
// Print messages for debugging
console.log('Hello, World!');
console.log('The page loaded.');

// Check a value
let name = 'Amara';
console.log(name);  // prints: Amara

// See errors
console.error('Something went wrong');
```

**First rule of JavaScript debugging:** Check the console. Always. Every time.

---

## Concept 4 — Variables

```javascript
// const — cannot be reassigned (use this by default)
const greeting = 'Hello';
const maxItems = 10;

// let — can be reassigned (use when the value will change)
let count = 0;
count = count + 1;  // allowed

// NEVER use var — it has confusing scope rules
// var name = 'old way';  // avoid
```

**Rule of thumb:** Start with `const`. Change to `let` only if you get an error.

---

## Concept 5 — Data Types

```javascript
// String — text in quotes
const name = 'Amara';
const message = "Welcome to the course!";
const template = `Hello, ${name}!`;  // template literal — embeds variables

// Number
const age = 22;
const price = 9.99;

// Boolean
const isLoggedIn = true;
const hasError = false;

// null — intentionally empty
const selectedItem = null;

// undefined — not yet assigned
let result;  // result is undefined

// Array — list of values
const skills = ['HTML', 'CSS', 'JavaScript'];
console.log(skills[0]);  // 'HTML' (zero-indexed)

// Object — key-value pairs
const student = {
  name: 'Kofi',
  module: 8,
  isActive: true
};
console.log(student.name);    // 'Kofi'
console.log(student['module']);  // 8
```

---

## Concept 6 — Functions

```javascript
// Declare a function
function greet(name) {
  return `Hello, ${name}! Welcome to the classroom.`;
}

// Call the function
const message = greet('Amara');
console.log(message);  // Hello, Amara! Welcome to the classroom.

// Arrow function (modern shorthand)
const double = (number) => number * 2;
console.log(double(5));  // 10

// Function with no return — just runs code
function showAlert(text) {
  alert(text);
}
```

---

## Concept 7 — Selecting DOM Elements

The DOM (Document Object Model) is the live HTML tree JavaScript can read and modify.

```javascript
// Select ONE element (returns the first match)
const heading = document.querySelector('h1');
const navMenu = document.querySelector('.nav-links');
const hero = document.querySelector('#hero');

// Select ALL matching elements (returns a NodeList)
const allCards = document.querySelectorAll('.card');
const allLinks = document.querySelectorAll('nav a');

// Loop through all selected elements
allCards.forEach(function(card) {
  console.log(card);
});
```

---

## Concept 8 — Events

Events are things the user does. You listen for them with `addEventListener`.

```javascript
const button = document.querySelector('.btn-toggle');

// Click event
button.addEventListener('click', function() {
  console.log('Button was clicked!');
});

// Arrow function version (same thing)
button.addEventListener('click', () => {
  console.log('Clicked!');
});

// Common event types:
// 'click'      → user clicks
// 'submit'     → form submitted
// 'input'      → user types in an input
// 'change'     → select/checkbox changes
// 'mouseover'  → mouse moves over element
// 'keydown'    → keyboard key pressed
```

---

## Concept 9 — Modifying the DOM

```javascript
const heading = document.querySelector('h1');
const body = document.querySelector('body');
const card = document.querySelector('.card');

// Change text content (SAFE — no HTML injection)
heading.textContent = 'New Heading Text';

// Add, remove, toggle CSS classes
body.classList.add('dark-mode');
body.classList.remove('dark-mode');
body.classList.toggle('dark-mode');  // adds if missing, removes if present

// Check if a class exists
if (body.classList.contains('dark-mode')) {
  console.log('Dark mode is on');
}

// Change a CSS style directly (use sparingly — prefer classes)
card.style.display = 'none';
card.style.backgroundColor = '#f8fafc';
```

---

## Project 1 — Dark Mode Toggle

```html
<!-- Add this button to your nav -->
<button class="btn-theme" id="theme-toggle" aria-label="Toggle dark mode">
  🌙 Dark Mode
</button>
```

```css
/* Light mode (default) */
:root {
  --color-bg:   #ffffff;
  --color-text: #1e293b;
}

/* Dark mode — applied when .dark-mode is on <body> */
body.dark-mode {
  --color-bg:   #0f172a;
  --color-text: #e2e8f0;
}

body {
  background-color: var(--color-bg);
  color: var(--color-text);
  transition: background-color 0.3s, color 0.3s;
}

.btn-theme {
  cursor: pointer;
  padding: 0.5rem 1rem;
  border: 1px solid currentColor;
  border-radius: 6px;
  background: transparent;
  color: inherit;
  font-size: 0.875rem;
}
```

```javascript
const toggleButton = document.querySelector('#theme-toggle');

toggleButton.addEventListener('click', () => {
  // Toggle the class on body
  document.body.classList.toggle('dark-mode');

  // Update button text to match current state
  const isDark = document.body.classList.contains('dark-mode');
  toggleButton.textContent = isDark ? '☀️ Light Mode' : '🌙 Dark Mode';

  // Save preference so it persists on page reload
  localStorage.setItem('theme', isDark ? 'dark' : 'light');
});

// On page load: restore saved preference
const savedTheme = localStorage.getItem('theme');
if (savedTheme === 'dark') {
  document.body.classList.add('dark-mode');
  toggleButton.textContent = '☀️ Light Mode';
}
```

---

## Project 2 — Form Validation

```html
<form id="contact-form" novalidate>
  <div class="field">
    <label for="fname">Full name</label>
    <input type="text" id="fname" name="fname">
    <span class="error-msg" id="fname-error"></span>
  </div>
  <div class="field">
    <label for="femail">Email address</label>
    <input type="email" id="femail" name="femail">
    <span class="error-msg" id="femail-error"></span>
  </div>
  <button type="submit">Send</button>
</form>
```

```javascript
const form = document.querySelector('#contact-form');

form.addEventListener('submit', function(event) {
  event.preventDefault();  // stop the form from reloading the page

  const name = document.querySelector('#fname');
  const email = document.querySelector('#femail');
  const nameError = document.querySelector('#fname-error');
  const emailError = document.querySelector('#femail-error');

  let isValid = true;

  // Validate name
  if (name.value.trim() === '') {
    nameError.textContent = 'Please enter your full name.';
    name.classList.add('input--error');
    isValid = false;
  } else {
    nameError.textContent = '';
    name.classList.remove('input--error');
  }

  // Validate email
  const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  if (!emailPattern.test(email.value)) {
    emailError.textContent = 'Please enter a valid email address.';
    email.classList.add('input--error');
    isValid = false;
  } else {
    emailError.textContent = '';
    email.classList.remove('input--error');
  }

  if (isValid) {
    console.log('Form is valid — would submit here');
    form.reset();
  }
});
```

---

## Exercises

### Exercise 8-A — Console Basics (Guided)
In `script.js`, write 5 `console.log` statements:
- Your name
- Current module number
- The result of 100 + 200 + 300
- A template literal: `I am learning ${skill} in module ${number}`
- An array of 3 things you've learned so far

### Exercise 8-B — DOM + Events (Semi-guided)
Add a button to your page. When clicked, it changes the `<h1>` text.
Hint: `querySelector` + `addEventListener('click')` + `textContent`

### Exercise 8-C — Dark Mode (Challenge)
Build the dark mode toggle from the example above.
Extension: save the preference to `localStorage` so it persists on reload.

### Exercise 8-D — Form Validator (Milestone Prep)
Build the contact form validator from the example above.
Extension: add a third field (message textarea, minimum 20 characters).

---

## Milestone Assessment

Submit a Pull Request with both projects working:
1. Dark mode button — toggles classes, updates button text, saves to localStorage
2. Form validator — specific error messages per field, shows/hides on each submit attempt

Include a screen recording (Zoom recording or Loom) showing both working.
