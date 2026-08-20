# Toolbox 2: JavaScript Essentials

This document contains everything you need for this toolbox — resources, exercises, starter code, and what "done" looks like for each one. Work through it in order, top to bottom.

**These exercises are practice, not something you submit.** Use the "You're done when" checklist under each one to self-check your work as you go.

> 📌 **What you actually submit:** at the end of your Quarter, you'll submit one **Artifact** — a GitHub repo link and a screen recording of your working project (locally deployed is fine), or a slide presentation. It's built from your Problem Brief work, not tied to any single toolbox — so nothing in Toolbox 2 gets submitted on its own.

This toolbox teaches core JavaScript — syntax, DOM manipulation, event handling, and basic browser APIs like `localStorage` and `Fetch` — without relying on frameworks. It also introduces Bootstrap for quickly styling responsive layouts. By the end, you'll move from reading and watching to building and shipping a real, working project.

**Goal:** Enable dynamic behavior on web pages using modern JavaScript, no frameworks required.

**Quick self-check:** if you can already write a function that shows or hides a paragraph when a button is clicked, you may be able to move through Modules 1–2 faster than the estimates below.

---

## What You'll Learn

By the end of this toolbox, you'll be able to:

- Explain core JavaScript syntax and concepts — variables, data types, functions, loops, and ES6+ features like arrow functions, `let`/`const`, and template literals
- Manipulate the DOM to select, create, update, and remove HTML elements in response to user actions
- Apply event listeners to handle clicks, form submissions, and keypresses
- Use `localStorage` and the Fetch API to save, retrieve, and persist data across browser sessions
- Build and debug a real JavaScript application — styled with Bootstrap, checked with Chrome DevTools — and ship it as evidence of what you've learned

---

## How to Use This Document

Each module has curated resources to read/watch, followed by three exercises of increasing difficulty:

- **Warm-up** — gets you comfortable with the basics
- **Core** — the main skill for that module
- **Stretch** — pushes further, closer to real-world complexity

Do them in order within a module. All three modules feed into one final **Integrative Project** at the end.

---

## Module 1: Modern JavaScript Syntax (ES6+ Features)

### Resources

| Resource | Type |
|---|---|
| [JavaScript Basics (MDN)](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps) | 📖 Read |
| [JavaScript Crash Course — Traversy Media](https://www.youtube.com/watch?v=hdI2bqOjy3c) | 🎥 Watch |
| [Variables, Functions, and Loops — W3Schools](https://www.w3schools.com/js/js_intro.asp) | 📖 Read |
| [ES6+ Cheatsheet](https://devhints.io/es6) | 📖 Reference |

### Exercise: Declare Variables and Format a Greeting *(Warm-up — 20–30 min)*

**Scenario:** You're setting up a few pieces of data for a simple profile card on a webpage.

**Instructions:**
1. Copy the starter code below into a file called `script.js`.
2. Declare a name (string) using `const`, an age (number) using `let`, and an `isMember` (boolean) using `let`.
3. Use a template literal (backticks with `${}`) to build a greeting string that includes the name and age.
4. Log the greeting to the console using `console.log()`.
5. Try reassigning the `const` variable to a new value and observe the error message in the console.

```js
// TODO: declare your variables here
// const name = ...
// let age = ...
// let isMember = ...

// TODO: build a greeting using a template literal
// const greeting = ...;

// TODO: log the greeting to the console
```

**You're done when:**
- [ ] Three variables are declared, with `const` used for the value that never changes and `let` used for the others
- [ ] The greeting string is built using a template literal, not string concatenation with `+`
- [ ] `console.log()` prints the greeting without errors
- [ ] Reassigning the `const` variable produces a `TypeError` in the console

---

### Exercise: Write Functions to Summarize a List of Numbers *(Core — 30–45 min)*

**Scenario:** You're building a small utility that summarizes a list of order quantities.

**Instructions:**
1. Copy the starter code below into your editor.
2. Write a function declaration called `sumArray` that takes an array of numbers and returns their total using a loop.
3. Write an arrow function called `averageArray` that takes an array of numbers and returns their average.
4. Call both functions using the provided `numbers` array and log the results using template literals.
5. Add a `for...of` loop that logs each number in the array multiplied by 2.

```js
const numbers = [4, 8, 15, 16, 23, 42];

// TODO: write sumArray as a function declaration, using a loop
function sumArray(nums) {

}

// TODO: write averageArray as an arrow function
const averageArray = (nums) => {

};

// TODO: call both functions and log the results with template literals

// TODO: use a for...of loop to log each number doubled
```

**You're done when:**
- [ ] `sumArray` returns the correct total for the `numbers` array
- [ ] `averageArray` is written as an arrow function and returns the correct average
- [ ] Both results are logged using template literals
- [ ] A `for...of` loop logs each number in `numbers` multiplied by 2

---

### Exercise: Refactor a Product Report with ES6+ Features *(Stretch — 30–45 min)*

**Scenario:** You've inherited an older script that formats a list of product records, and you need to modernize it.

**Instructions:**
1. Copy the starter code below into your editor.
2. Replace every `var` with `let` or `const`, choosing whichever fits based on whether the value is reassigned.
3. Convert the string concatenation inside `formatProduct` into a template literal.
4. Rewrite `formatProduct` as an arrow function assigned to a `const`.
5. Inside the loop, use array destructuring to pull `name` and `price` out of each product object.
6. Log the formatted output for all three products and confirm it matches the original wording.

```js
var products = [
  { name: "Notebook", price: 3.5 },
  { name: "Pen", price: 1.25 },
  { name: "Backpack", price: 24.99 }
];

var formatProduct = function(product) {
  return product.name + " costs $" + product.price;
};

for (var i = 0; i < products.length; i++) {
  console.log(formatProduct(products[i]));
}
```

**You're done when:**
- [ ] No `var` keywords remain anywhere in the refactored code
- [ ] `formatProduct` is an arrow function that builds its return value with a template literal
- [ ] Array destructuring is used to extract `name` and `price` from at least one product inside the loop
- [ ] The console output for all three products matches the original wording

---

## Module 2: DOM Manipulation & Event Handling

### Resources

| Resource | Type |
|---|---|
| [DOM Explained (JavaScript.info)](https://javascript.info/dom-nodes) | 📖 Read |
| [DOM Events (MDN)](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) | 📖 Read |
| [Interactive To-Do List Walkthrough](https://www.youtube.com/watch?v=3PHXvlpOkf4) | 🎥 Watch |

### Exercise: Select and Update Page Text *(Warm-up — 20–30 min)*

**Scenario:** You're updating a status message on a simple info page after it finishes loading.

**Instructions:**
1. Copy the starter HTML below into a file called `index.html`.
2. In a linked `script.js` file, use `document.querySelector` to select the element with `id="status"`.
3. Change that element's `textContent` to `"Loaded successfully"`.
4. Use `document.querySelector` to select the element with `id="title"` and change its `style.color` to a color of your choice.
5. Open the page in a browser and confirm both changes appear.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Status Page</title>
</head>
<body>
  <h1 id="title">Page Status</h1>
  <p id="status">Loading...</p>
  <script src="script.js"></script>
</body>
</html>
```

**You're done when:**
- [ ] The element with `id="status"` displays "Loaded successfully" when the page opens
- [ ] The element with `id="title"` has a text color different from the browser default
- [ ] Both changes are made using `document.querySelector`, not by editing the HTML directly
- [ ] No errors appear in the browser console

---

### Exercise: Add and Remove List Items on Click *(Core — 30–45 min)*

**Scenario:** You're building a simple checklist widget where users can add items and remove them by clicking.

**Instructions:**
1. Copy the starter code below into your project.
2. Add a click event listener to the button with `id="add-btn"`.
3. When clicked, read the value from the input with `id="item-input"`, create a new `<li>` containing that text, and append it to the `<ul id="item-list">`.
4. Clear the input field after adding the item.
5. Add a click event listener to each new `<li>` so that clicking it removes that item from the list.
6. Prevent blank items from being added when the input is empty.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Checklist</title>
</head>
<body>
  <input id="item-input" type="text" placeholder="New item">
  <button id="add-btn">Add</button>
  <ul id="item-list"></ul>

  <script>
    const addBtn = document.querySelector("#add-btn");
    const input = document.querySelector("#item-input");
    const list = document.querySelector("#item-list");

    // TODO: add a click event listener to addBtn that:
    // - ignores empty input
    // - creates a new <li> with the input's value
    // - appends it to list
    // - clears the input
    // - adds a click listener on the new <li> to remove it when clicked
  </script>
</body>
</html>
```

**You're done when:**
- [ ] Clicking "Add" with text in the input creates a new `<li>` showing that text
- [ ] The input field clears after each item is added
- [ ] Clicking any `<li>` in the list removes it from the page
- [ ] Clicking "Add" with an empty input does not create a blank `<li>`

---

### Exercise: Validate and Submit a Form Without Reloading *(Stretch — 40–50 min)*

**Scenario:** You're building a small sign-up form that needs to validate input and respond without a full page reload.

**Instructions:**
1. Copy the starter code below into your project.
2. Add a submit event listener to the `<form id="signup-form">` that prevents the default page reload.
3. Inside the listener, check that the `<input id="email">` value contains an "@" character.
4. If valid, display a success message inside `<div id="form-message">` and reset the form.
5. If invalid, display an error message inside `<div id="form-message">` without resetting the form.
6. Add a keypress listener on the email input that clears any existing message as soon as the user starts typing again.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Sign Up</title>
</head>
<body>
  <form id="signup-form">
    <input id="email" type="text" placeholder="Enter your email">
    <button type="submit">Sign Up</button>
  </form>
  <div id="form-message"></div>

  <script>
    const form = document.querySelector("#signup-form");
    const emailInput = document.querySelector("#email");
    const message = document.querySelector("#form-message");

    // TODO: add a submit event listener that prevents default,
    // validates the email, and updates the message div

    // TODO: add a keypress listener on emailInput that clears the message
  </script>
</body>
</html>
```

**You're done when:**
- [ ] Submitting the form never reloads the page
- [ ] Submitting a value without "@" shows an error message and keeps the form filled in
- [ ] Submitting a value with "@" shows a success message and clears the form
- [ ] Typing in the email field after a message is shown clears that message

---

## Module 3: Basic Browser APIs (Fetch API, localStorage)

### Resources

| Resource | Type |
|---|---|
| [localStorage Tutorial — Web Dev Simplified](https://www.youtube.com/watch?v=GihQAC1I39Q) | 🎥 Watch |
| [localStorage API Docs (MDN)](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) | 📖 Reference |
| [Using the Fetch API (MDN)](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) | 📖 Read |

### Exercise: Save and Load a Preference with localStorage *(Warm-up — 20–30 min)*

**Scenario:** You're adding a simple setting that remembers a user's preferred display name across visits.

**Instructions:**
1. Copy the starter code below into your project.
2. Add a click listener to the button with `id="save-btn"` that saves the value of the input with `id="name-input"` to `localStorage` under the key `"displayName"`.
3. When the page loads, check `localStorage` for `"displayName"` and, if it exists, show it inside `<p id="greeting">` as `"Welcome back, [name]!"`.
4. If no value exists yet, leave the greeting blank.
5. Save a name, then refresh the page to confirm it persists.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Preferences</title>
</head>
<body>
  <input id="name-input" type="text" placeholder="Your name">
  <button id="save-btn">Save</button>
  <p id="greeting"></p>

  <script>
    const saveBtn = document.querySelector("#save-btn");
    const nameInput = document.querySelector("#name-input");
    const greeting = document.querySelector("#greeting");

    // TODO: on page load, check localStorage for "displayName"
    // and update greeting if it exists

    // TODO: add a click listener to saveBtn that stores
    // the input's value in localStorage under "displayName"
  </script>
</body>
</html>
```

**You're done when:**
- [ ] Clicking "Save" stores the entered name in `localStorage` under the key `"displayName"`
- [ ] Reloading the page after saving shows "Welcome back, [name]!" in the greeting element
- [ ] Clearing `localStorage` (via DevTools) and reloading shows a blank greeting again
- [ ] No console errors appear during save or load

---

### Exercise: Persist a List of Notes with localStorage *(Core — 40–50 min)*

**Scenario:** You're extending a notes widget so that saved notes stay on the page after a refresh.

**Instructions:**
1. Copy the starter code below into your project.
2. Write a `render(notes)` function that clears and rebuilds the `<ul>` from the `notes` array, making each `<li>` removable on click.
3. On page load, read any saved notes from `localStorage` using `JSON.parse` and render them.
4. Add a click listener to the "Add Note" button that pushes the input's value into the `notes` array, saves the array to `localStorage` using `JSON.stringify`, re-renders the list, and clears the input.
5. Confirm that clicking a note removes it from both the page and `localStorage`.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Notes</title>
</head>
<body>
  <input id="note-input" type="text" placeholder="New note">
  <button id="add-note-btn">Add Note</button>
  <ul id="notes-list"></ul>

  <script>
    const input = document.querySelector("#note-input");
    const addBtn = document.querySelector("#add-note-btn");
    const list = document.querySelector("#notes-list");
    let notes = [];

    // TODO: load notes from localStorage (JSON.parse) on page load
    // and render them

    // TODO: write a render(notes) function that clears and rebuilds
    // the <ul> from the notes array, with each <li> removable on click

    // TODO: add a click listener to addBtn that pushes the input's
    // value into notes, saves to localStorage (JSON.stringify),
    // re-renders, and clears the input
  </script>
</body>
</html>
```

**You're done when:**
- [ ] Adding a note updates both the visible list and `localStorage`
- [ ] Reloading the page shows the previously saved notes still in the list
- [ ] Clicking a note removes it from the list and from `localStorage`
- [ ] `localStorage` stores the notes as a single JSON string, not as separate keys

---

### Exercise: Fetch and Display Data from a Public API *(Stretch — 40–50 min)*

**Scenario:** You're building a page that shows a piece of external data pulled live from a public API.

**Instructions:**
1. Copy the starter code below into your project.
2. Add a click listener to the button with `id="load-btn"` that uses `fetch()` to request data from `https://jsonplaceholder.typicode.com/users/1`.
3. Parse the response as JSON and display the user's name and email inside `<div id="user-card">`.
4. Handle a failed request (for example using `.catch` or try/catch) by showing an error message inside `<div id="user-card">` instead of leaving it blank.
5. Disable the button while the request is in progress and re-enable it once the request finishes, whether it succeeds or fails.
6. Open Chrome DevTools and confirm there are no unhandled promise rejections in the console.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>User Lookup</title>
</head>
<body>
  <button id="load-btn">Load User</button>
  <div id="user-card"></div>

  <script>
    const loadBtn = document.querySelector("#load-btn");
    const card = document.querySelector("#user-card");

    // TODO: add a click listener to loadBtn that:
    // - disables the button
    // - fetches https://jsonplaceholder.typicode.com/users/1
    // - displays name and email in card on success
    // - shows an error message in card on failure
    // - re-enables the button when done
  </script>
</body>
</html>
```

**You're done when:**
- [ ] Clicking "Load User" displays the fetched user's name and email inside the user-card element
- [ ] The button is disabled during the request and re-enabled afterward, regardless of outcome
- [ ] Simulating a failed request (e.g., using an invalid URL) shows an error message instead of a blank card
- [ ] No unhandled promise rejections appear in the console

---

## Supporting Tools: Debugging & Bootstrap

Not a graded module on its own, but you'll need both for the Integrative Project below.

| Resource | Type |
|---|---|
| [Debugging with Chrome DevTools](https://developer.chrome.com/docs/devtools/) | 📖 Read |
| [`console.log()` and Breakpoints Guide](https://www.freecodecamp.org/news/javascript-debugging-guide/) | 📖 Read |
| [Bootstrap Getting Started](https://getbootstrap.com/docs/5.3/getting-started/introduction/) | 📖 Read |

---

## Optional Further Reading

| Resource | Type |
|---|---|
| [Eloquent JavaScript — Marijn Haverbeke](https://eloquentjavascript.net/) | 📖 Book (free, full-length) |

This one's a real book, not a quick reference — good if you want a deeper, more thorough grounding in JavaScript beyond what the exercises require. Optional, not required to finish the toolbox.

---

## Integrative Project: Build a Persistent To-Do List with Bootstrap Styling *(60–90 min)*

**Scenario:** You're shipping a small working app to show as evidence of what you've learned: a to-do list that remembers items between visits.

This is the biggest single exercise in the toolbox — everything from Modules 1–3 comes together here, and it's good practice for the kind of project you'll eventually build as your Artifact. Same as the rest of this document, it's still practice — self-check it with the criteria below, not something you submit on its own.

**Instructions:**
1. Copy the starter HTML below into your project — it already includes a Bootstrap CDN link and a form styled with Bootstrap classes.
2. Write a `render(todos)` function that rebuilds the Bootstrap list group from a `todos` array, where each item is an object like `{ text, completed }`.
3. On page load, read any saved todos from `localStorage` (`JSON.parse`) and render them.
4. Add a submit listener on the form that prevents default, adds a new todo to the array, saves it to `localStorage` (`JSON.stringify`), re-renders the list, and clears the input.
5. Use event delegation on the list to handle clicks: clicking an item's text toggles a "completed" style (e.g., Bootstrap's `text-decoration-line-through`), and clicking a delete control removes that item.
6. Save the updated todos array to `localStorage` every time it changes.
7. Open Chrome DevTools and add `console.log()` statements to trace when items are added, completed, and deleted; once you've confirmed the app works, remove or comment out those logs.
8. Reload the page to confirm your list is still there.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>To-Do List</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body class="container py-4">
  <h1 class="mb-3">My To-Do List</h1>
  <form id="todo-form" class="d-flex gap-2 mb-3">
    <input id="todo-input" type="text" class="form-control" placeholder="Add a task">
    <button type="submit" class="btn btn-primary">Add</button>
  </form>
  <ul id="todo-list" class="list-group"></ul>

  <script>
    const form = document.querySelector("#todo-form");
    const input = document.querySelector("#todo-input");
    const list = document.querySelector("#todo-list");
    let todos = [];

    // TODO: load todos from localStorage on page load and render them

    // TODO: write a render(todos) function that rebuilds the list-group
    // from the todos array (each item has { text, completed })

    // TODO: add a submit listener on form that prevents default,
    // adds a new todo, saves to localStorage, re-renders, clears input

    // TODO: use event delegation on list to handle clicks for
    // toggling "completed" and deleting items
  </script>
</body>
</html>
```

**You're done when:**
- [ ] Adding a task via the form displays it in a Bootstrap-styled list group
- [ ] Reloading the page preserves all previously added tasks
- [ ] Clicking a task's text toggles a visible "completed" style, such as strikethrough
- [ ] Deleting a task removes it from both the page and `localStorage`
- [ ] `console.log()` was used during development to verify behavior in DevTools, per the instructions, before being cleaned up

---

*Stuck on anything? Email talassify@gmail.com or drop a message in the [help-javascript-essentials](https://discord.com/channels/1394725774329778267/1535360352718557224) Discord channel. We'd rather answer a "dumb question" now than have you stall out on your progress.*
