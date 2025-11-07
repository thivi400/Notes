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
- **ReactDOM** renders components to the page.

### Initial Setup

**indes.jsx**
```jsx
import {createRoot} from "react-dom/client";
import App from "./App.jsx"

const root = createRoot(doctument.getElementById("root"))
function App() {
  return <h1>Hello React!</h1>;
}


root.render(<App />);
