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
- Use **className** instead of **class** for CSS classes.
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

## 🧠 Quiz -- try to answer by yourself


Q1. Where does React put all of the elements I create in JSX when I call `root.render()`? 

**Answer:**     
All the elements I render get put inside the div with the id of "root" (or whatever other element I might select when calling createRoot)
<br>
<br>

Q2. What would show up in my console if I were to run this line of code:
```
console.log(<h1>Hello world!</h1>)
```

**Answer:**     
An object! (Hello world!)   
Unlike creating an HTML element in vanilla DOM JS, what gets created from the JSX we have in our React code is a plain JS object that React will use to fill in the view.
<br>
<br>

Q3. What's wrong with this code:
```
root.render(
        <h1>Hi there</h1>
        <p>This is my website!</p>
)
```

**Answer:**    
You can only render 1 parent element at a time. That parent element can have as many children elements as you want.   
wrap it under ```<section> </section>```
<br>
<br>

Q4. What does it mean for something to be "declarative" instead of "imperative"?

**Answer:**    
```Imperative``` --> we need to give specific step-by-step instructions on how to accomplish a task.   
```Declarative``` -->  we can write our code to simply "describe" *what* should show up on the page and allow the rool (React, e.g.) to handle the details on *how* to put those things on the page.
<br>
<br>

Q5. What does it mean for something to be "composable"?

**Answer:**    
We have small pieces that we can put together to make something larger or greater than the individual pieces themselves.
<br>   
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
If you use them in separate files, export components with 
```jsx
export default ComponentName(){
   return()
}
```
     
<br>

## 🧠 Quiz -- try to answer by yourself


Q1. What is a React component?

**Answer:**  
A function that returns React elements. (UI)   
<br>
<br>

Q2. What's wrong with this code?
```
function myComponent() {
    return (
        <small>I'm tiny text!</small>
    )
}
```

**Answer:**     
MyComponent -- First letter must Capital
<br>
<br>

Q3. What's wrong with this code?
```
function Header() {
    return (
        <header>
            <img src="./react-logo.png" width="40px" alt="React logo" />
        </header>
    )
}

root.render(Header())
```

**Answer:**  
```root.render(<Header/>)```
<br>
<br>
<hr>
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
<br>
<br>

**index.jsx**
```jsx
import {createRoot} from "react-dom/client";
import App from "./App.jsx"
const root = createRoot(doctument.getElementById("root"))

root.render(   
    <App />
);
```
<br>
<br>

**App.jsx**
```jsx
import "./index.css"
export default function App(){
  return (
    <>
    </>
}
```
<br>
<br>

```index.js``` ==> Setting up things like root
```App.js``` ==> Parent to every Component
<br>
<br>
<br>
<hr>
<br>

# 📝 Data-Driven React -- Reusable components

## 4️⃣ Props (Properties)

- Props are how components receive data.
- Think of props as function parameters for components.
- They make components dynamic and reusable.
- Props are read-only; they cannot be modified by the child component.
- Use object destructuring to extract specific props.
- Props flow one-way — from parent to child.
- Components can receive any kind of data as props: strings, numbers, arrays, objects, or even functions.


<br>

## 🧠 Quiz -- try to answer by yourself
<br>

Q1. What do props help us accomplish?

**Answer:**    
Make a component more reusable.
<br>
<br>

Q2. How do you pass a prop into a component?

**Answer:**    
```<MyAwesomeHeader title="???" />```
<br>
<br>

Q3. Can I pass a custom prop (e.g. `blahblahblah={true}`) to a native DOM element? (e.g.```<div blahblahblah={true}>```) Why or why not?

**Answer:**    
No, because the JSX we use to describe native DOM elements will be turned into REAL DOM elements by React. And real DOM elements only have the properties/attributes specified in the HTML specification.   
(Which doesn't include properties like `blahblahblah`)
<br>
<br>

Q4. How do I receive props in a component?

**Answer:**  
```
function Navbar(props) {
    console.log(props.blahblahblah)
    return (
        <header>
            ...
        </header>
    )
}
```
<br>
<br>

Q5. What data type is `props` when the component receives it?

**Answer:**    
An object!
<br>
<br>
