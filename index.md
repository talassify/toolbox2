# Talassify Toolbox 2: JavaScript Essentials — Resource List (plus Boostrap library)

This toolbox focuses on learning core JavaScript concepts, manipulating the DOM, and storing data using localStorage — all without frameworks.

---

## JavaScript Fundamentals

- [JavaScript Basics (MDN)](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps)  
- [JavaScript Crash Course – Traversy Media (YouTube)](https://www.youtube.com/watch?v=hdI2bqOjy3c)  
- [Variables, Functions, and Loops – W3Schools](https://www.w3schools.com/js/js_intro.asp)  
- [ES6+ Cheatsheet](https://devhints.io/es6)

---

## DOM Manipulation & Events

- [DOM Explained (JavaScript.info)](https://javascript.info/dom-nodes)  
- [DOM Events (MDN)](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)  
- [Interactive To-Do List Walkthrough](https://www.youtube.com/watch?v=3PHXvlpOkf4)

---

## Working with LocalStorage


- [LocalStorage Tutorial – Web Dev Simplified](https://www.youtube.com/watch?v=GihQAC1I39Q)  
- [localStorage API Docs (MDN)](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)

---

## Debugging and Developer Tools

- [Debugging with Chrome DevTools](https://developer.chrome.com/docs/devtools/)  
- [`console.log()` and Breakpoints Guide](https://www.freecodecamp.org/news/javascript-debugging-guide/)

---

## Bootstrap
Bootstrap is the most popular HTML, CSS, and JS framework for developing responsive, mobile first projects on the web.
- [Bootstrap Getting Started](https://getbootstrap.com/docs/5.3/getting-started/introduction/)


---

## To-Do List App mini project

**A. Starter JavaScript file**
Copy & Paste the following code block to `mini-project_template.js`

```
// 📦 Talassify Mini Project: To-Do List App (JavaScript Starter)

// DOM References
const form = document.querySelector('#todo-form');
const input = document.querySelector('#todo-input');
const list = document.querySelector('#todo-list');

// Load saved tasks from localStorage
let todos = JSON.parse(localStorage.getItem('todos')) || [];
renderTodos();

// Add new task
form.addEventListener('submit', function (e) {
  e.preventDefault();
  const task = input.value.trim();
  if (task === '') return;

  todos.push(task);
  saveTodos();
  renderTodos();
  input.value = '';
});


// Save to localStorage
function saveTodos() {
  localStorage.setItem('todos', JSON.stringify(todos));
}
// Display tasks
function renderTodos() {
  list.innerHTML = '';
  todos.forEach((todo, index) => {
    const li = document.createElement('li');
    li.textContent = todo;

    // Delete button
    const delBtn = document.createElement('button');
    delBtn.className = 'delete-btn'
    delBtn.textContent = '❌';
    delBtn.onclick = () => {
      todos.splice(index, 1);
      saveTodos();
      renderTodos();
    };

    li.appendChild(delBtn);
    list.appendChild(li);
  });
}
```

**B. Sample HTML Structure (To test the script)**
```
<form id="todo-form">
    <input id="todo-input" placeholder="Enter task" required />
    <button>Add Task</button>
</form>
```

**C. CSS Style for your To-Do List App mini project**
 `styles.css` file for the To-Do List App mini project, styled to be clean, mobile-friendly, and easy to expand.
 

```

/* ===== Reset & Base Styles ===== */
body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  padding: 2rem;
  background: #f4f6f8;
  color: #333;
  max-width: 500px;
  margin: auto;
}

h1 {
  text-align: center;
  color: #1f4e79;
}

form {
  display: flex;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

input {
  flex: 1;
  padding: 0.75rem;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  background-color: #29c282;
  color: white;
  border: none;
  padding: 0.75rem 1rem;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #90c6af;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  background: white;
  padding: 0.75rem 1rem;
  border: 1px solid #ddd;
  border-radius: 5px;
  margin-bottom: 0.5rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

li button {
  padding: 0.25rem 0.5rem;
  border-radius: 3px;
  font-size: 0.9rem;
}

li button:hover {
  background-color: #e2a4a9;
}

.delete-btn {
    background: none;
}
```

---

## Bonus Practice Projects

- [Frontend Mentor – Beginner Projects](https://www.frontendmentor.io/challenges?difficulty=1)  
- [JavaScript 30 (Free Projects by Wes Bos)](https://javascript30.com/)  
- [Codewell Challenges](https://www.codewell.cc/)  
- [JS Challenges & Exercises – Edabit](https://edabit.com/challenges/javascript)


---

Built with ♥ by **Talassify**
