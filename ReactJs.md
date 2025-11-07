# 📘 React Notes 
Source: Scrimba React Course

---

## 1️⃣ Introduction to React

- **React** is a **JavaScript library** for building dynamic user interfaces.
- Developed by **Facebook (Meta)**.
- Focuses on building **reusable components**.
- It uses a **declarative** approach — you describe *what* you want the UI to look like, and React updates the DOM for you.
- React builds a **virtual DOM** (a lightweight copy of the real DOM) to efficiently update only what changes.

### 💡 Key Points
- React apps are composed of **components** (functions that return JSX).
- **JSX (JavaScript XML)** lets you write HTML-like syntax directly in JavaScript.
- **JSX** = JavaScript + XML-like syntax.
- React elements must return a single root element (wrap multiple elements in a <div> or <> fragment).
- JSX gets transpiled to JavaScript via Babel.
- **ReactDOM** renders components to the page.
<br>

## 2️⃣ JSX and Rendering Notes
- Use curly braces {} to insert JS inside JSX. Can be variables, functions, or calculations.
- Use className instead of class for CSS classes.
- JSX expressions must be closed properly (e.g., <img />).
- You can create reusable UI with functions that return JSX.
- Cannot use if statements directly inside JSX — use ternary or conditional rendering.
<br>
   
### ⚛️ React Philosophy: Declarative & Composable
| Concept | Meaning | Example |
|----------|----------|----------|
| **Composable** | Build UIs from small reusable components | `<Header /><Main /><Footer />` |
| **Declarative** | Describe what UI should look like based on state | `{isDarkMode ? "Dark" : "Light"}` |
<br>
   
## 3️⃣ Components Notes
- Components are reusable pieces of UI.
- In React, a component is just a JavaScript function that returns JSX.
- Components can be nested (one component used inside another).
- Two types:
  - Functional components (modern standard)
  - Class components (older, less common)
- Component names must start with a capital letter (e.g., Header, not header).
- Components help split UI into smaller, reusable pieces.
- Each component should have a single responsibility.

```jsx
function Header() {
  return <h1>My React App</h1>;
}
function Footer() {
  return <footer>© 2025 Pubs Learning React</footer>;
}
function App() {
  return (
    <div>
      <Header />
      <Footer/>
    </div>
)
```
Export components with ```export default ComponentName``` if you use them in separate files.   
<br>
    
## ⚙️ Initial Setup
**index.html**
```html
<head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet" >
  <link rel="stylesheet" href="./src/index.css" />
</head>
<body>
  <div id="root"></div>
  <script type="module" src="./src/index.jsx"></script>
</body>
</html>
```
Everything we doing will wrapped in the root element div.

**index.jsx**
```jsx
import {createRoot} from "react-dom/client";
import App from "./App.jsx"
const root = createRoot(doctument.getElementById("root"))

root.render(   
    <App />
);
```
**App.jsx**
```jsx
import "./index.css"
export default function App(){
  return (
    <>
    </>
}
```

## 🧠 Quiz -- try to answer by yourself
1. Where does React put all of the elements I create in JSX when I call `root.render()`?

All the elements I render get put inside the div with the id of "root" (or whatever other element I might select when calling createRoot)
<br>

2. What would show up in my console if I were to run this line of code:
```
console.log(<h1>Hello world!</h1>)
```
An object! (Hello world!)   
Unlike creating an HTML element in vanilla DOM JS, what gets created from the JSX we have in our React code is a plain JS object that React will use to fill in the view.
<br>

3. What's wrong with this code:
```
root.render(
        <h1>Hi there</h1>
        <p>This is my website!</p>
)
```
You can only render 1 parent element at a time. That parent element can have as many children elements as you want.   
wrap it under ```<section> </section>```
<br>

4. What does it mean for something to be "declarative" instead of "imperative"?
*Imperative* --> we need to give specific step-by-step instructions on how to accomplish a task.
*Declarative* -->  we can write our code to simply "describe" *what* should show up on the page and allow the rool (React, e.g.) to handle the details on *how* to put those things on the page.
<br>

5. What does it mean for something to be "composable"?
We have small pieces that we can put together to make something larger or greater than the individual pieces themselves.
