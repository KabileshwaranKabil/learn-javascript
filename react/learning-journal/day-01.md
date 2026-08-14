# Day 01 — React

**Date:** 14-08-2026
**Resources:** Bro Code — React JS Course; ChatGPT (troubleshooting, deeper explanations, and note refinement)

---

## 1. Creating a React Project with Vite

### 1.1 What is Vite?

**Vite** is a modern frontend build tool and development server. It provides a fast development environment for frameworks such as React.

When creating a React application with Vite, Vite sets up the basic project structure, development server, and build configuration for us.

### 1.2 Creating the Project

First, open a terminal in the directory where the project should be created.

Run:

```bash
npm create vite@latest
```

Vite will ask several questions, such as:

* Project name
* Framework → `React`
* Variant → `JavaScript` or `TypeScript`

Alternatively, the project can be created directly:

```bash
npm create vite@latest project-name
```

Then navigate into the project:

```bash
cd project-name
```

Install the project dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

The terminal will provide a local URL, usually similar to:

```text
http://localhost:5173/
```

### 1.3 Important npm Commands

| Command                  | Purpose                                        |
| ------------------------ | ---------------------------------------------- |
| `npm create vite@latest` | Creates a new Vite project                     |
| `npm install`            | Installs dependencies listed in `package.json` |
| `npm run dev`            | Starts the development server                  |
| `npm run build`          | Creates a production build                     |
| `npm run preview`        | Locally previews the production build          |

---

## 2. React Project Structure

A typical Vite + React project contains the following files and directories:

```text
project-name/
├── node_modules/
├── public/
├── src/
│   ├── assets/
│   ├── App.css
│   ├── App.jsx
│   ├── index.css
│   └── main.jsx
├── .gitignore
├── eslint.config.js
├── index.html
├── package.json
├── package-lock.json
├── README.md
└── vite.config.js
```

> The exact structure may vary depending on the Vite template and the choices made during project creation.

### 2.1 `node_modules/`

`node_modules` contains the packages installed for the project and their dependencies.

For example, React and Vite packages are installed here.

**Important:** We normally do **not** commit `node_modules` to GitHub because it can be very large and can be recreated from `package.json` and the lock file.

That is why `node_modules/` is normally included in `.gitignore`.

---

### 2.2 `public/`

The `public` directory contains static assets that can be served directly without going through the normal module-import process.

Examples include:

* Images
* Icons
* Favicons
* Other static files

For example:

```text
public/
├── favicon.svg
└── ...
```

Files placed directly inside `public` can generally be referenced using a root-relative path:

```jsx
<img src="/favicon.svg" alt="Favicon" />
```

For assets that are part of the application's module system, the `src/assets` directory is commonly used instead.

---

### 2.3 `src/`

`src` is the main development directory of the React application.

This is where most of the application's source code is written.

It can contain:

* React components
* JSX files
* JavaScript files
* CSS files
* Images and other imported assets
* Application logic

Example:

```text
src/
├── assets/
├── components/
├── App.jsx
├── App.css
├── index.css
└── main.jsx
```

As the project grows, it is useful to organize reusable components into a `components/` directory.

---

### 2.4 `index.html`

`index.html` is the main HTML document used by the Vite application.

Unlike traditional websites where we may write most of the page directly in HTML, React applications typically use this HTML file as the entry point where React mounts the application.

A simplified example:

```html
<div id="root"></div>
```

React uses this element as the mounting point for the application.

---

### 2.5 `main.jsx`

`main.jsx` is the JavaScript/JSX entry point of the React application.

A typical Vite React application contains code similar to:

```jsx
import { StrictMode } from 'react';
import { createRoot } from 'react-dom/client';
import App from './App.jsx';
import './index.css';

createRoot(document.getElementById('root')).render(
  <StrictMode>
    <App />
  </StrictMode>
);
```

The important concept is:

```text
index.html
    ↓
<div id="root">
    ↓
main.jsx
    ↓
<App />
    ↓
React component tree
```

---

### 2.6 `App.jsx`

`App.jsx` commonly contains the root `App` component.

Example:

```jsx
function App() {
  return (
    <h1>Hello React</h1>
  );
}

export default App;
```

The `App` component can then contain or render other components.

---

### 2.7 `.gitignore`

`.gitignore` specifies files and directories that Git should ignore.

For example:

```text
node_modules/
.env
dist/
```

This is important because some files should not be committed to a repository.

For example:

* `node_modules/` is unnecessary because dependencies can be reinstalled.
* `.env` may contain secrets such as API keys or database credentials.
* `dist/` is usually a generated production build and does not normally need to be committed.

**Important:** `.gitignore` does not protect a secret that has already been committed to Git. If a secret has already been pushed, it should be considered exposed and the credential should be rotated.

---

### 2.8 `package.json`

`package.json` contains important metadata and configuration for the project.

It can contain:

* Project name
* Version
* Scripts
* Dependencies
* Development dependencies
* Other npm configuration

Example:

```json
{
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  }
}
```

Dependencies may look like:

```json
"dependencies": {
  "react": "...",
  "react-dom": "..."
}
```

---

### 2.9 `package-lock.json`

`package-lock.json` records the exact dependency tree resolved by npm.

It helps ensure that installing the project on another machine produces a consistent dependency installation.

Therefore, unlike `node_modules`, the lock file is normally committed to Git.

---

### 2.10 `eslint.config.js`

ESLint is a static analysis tool used to identify potential problems and enforce coding conventions.

`eslint.config.js` contains the project's ESLint configuration.

It can help detect issues such as:

* Unused variables
* Incorrect patterns
* Potential bugs
* Code-quality problems

---

### 2.11 `vite.config.js`

`vite.config.js` contains configuration for Vite.

It can be used to configure things such as:

* Plugins
* Aliases
* Development-server behavior
* Build behavior
* Other Vite-specific settings

For React projects, the Vite React plugin is commonly configured here.

---

### 2.12 `README.md`

`README.md` provides documentation about the project.

It commonly contains:

* Project description
* Installation instructions
* How to run the project
* Technologies used
* Features
* Usage information

---

## 3. React Components

### 3.1 What is a Component?

**Components are the fundamental building blocks of React applications.**

A component is a reusable piece of UI that can contain:

* JSX markup
* JavaScript logic
* Data
* Event handling
* Styling

A simple component:

```jsx
function Welcome() {
  return <h1>Welcome to React</h1>;
}

export default Welcome;
```

Another component can use it:

```jsx
function App() {
  return (
    <>
      <Welcome />
    </>
  );
}

export default App;
```

### 3.2 Why Components?

Components allow a large interface to be divided into smaller, manageable pieces.

For example:

```text
Application
│
├── Navbar
├── Sidebar
├── MainContent
│   ├── UserCard
│   ├── ProductCard
│   └── PostCard
└── Footer
```

Instead of writing the entire interface in one large file, each logical part can be implemented as a reusable component.

### 3.3 Component Naming Convention

React component names should normally start with an uppercase letter.

Correct:

```jsx
function Header() {
  return <header>Header</header>;
}
```

Then:

```jsx
<Header />
```

Lowercase JSX names are generally interpreted as HTML elements:

```jsx
<header></header>
```

Therefore, use **PascalCase** for React component names:

```text
Header
Footer
UserProfile
ProductCard
NavigationBar
```

---

## 4. JSX

### 4.1 What is JSX?

**JSX stands for JavaScript XML.**

JSX is a syntax extension for JavaScript that allows us to write HTML-like markup inside JavaScript code.

Example:

```jsx
function App() {
  return <h1>Hello React</h1>;
}
```

JSX is **not HTML** and it is not literally XML. It is syntax that is transformed into JavaScript during the build process.

For example, conceptually:

```jsx
<h1>Hello React</h1>
```

is transformed into a JavaScript representation of that element.

### 4.2 JSX Allows JavaScript Expressions

JavaScript expressions can be embedded inside JSX using curly braces `{}`.

Example:

```jsx
function App() {
  const name = "Kabilesh";

  return <h1>Hello, {name}!</h1>;
}
```

Output:

```text
Hello, Kabilesh!
```

This is one of the important differences between writing traditional HTML and writing JSX.

---

## 5. `.jsx` Files

A `.jsx` file is a JavaScript file that contains JSX syntax.

Example:

```jsx
function App() {
  const message = "Learning React";

  return <h1>{message}</h1>;
}

export default App;
```

The statement that `.jsx` contains "JavaScript and XML code" is slightly inaccurate.

A better description is:

> **A `.jsx` file contains JavaScript code with JSX syntax, which allows HTML-like UI markup to be written inside JavaScript.**

JSX is ultimately transformed into JavaScript.

### `.js` vs `.jsx`

Both `.js` and `.jsx` can contain JavaScript.

The `.jsx` extension is commonly used when a file contains JSX so that the purpose of the file is immediately clear.

For example:

```text
App.jsx
Navbar.jsx
UserCard.jsx
```

---

## 6. React Fragments

### 6.1 The Problem

A React component must return a single root element.

This code is invalid:

```jsx
function App() {
  return (
    <Header />
    <Footer />
  );
}

export default App;
```

The problem is that the component is attempting to return two sibling elements directly.

---

### 6.2 Using a Fragment

A **React Fragment** allows multiple elements to be grouped without adding an unnecessary element to the DOM.

Using the shorthand syntax:

```jsx
function App() {
  return (
    <>
      <Header />
      <Footer />
    </>
  );
}

export default App;
```

Here:

```jsx
<>
  ...
</>
```

is a shorthand for:

```jsx
<React.Fragment>
  ...
</React.Fragment>
```

Therefore, the following are equivalent:

```jsx
<>
  <Header />
  <Footer />
</>
```

and:

```jsx
<React.Fragment>
  <Header />
  <Footer />
</React.Fragment>
```

### 6.3 Why Use Fragments?

Suppose we used a `<div>` instead:

```jsx
function App() {
  return (
    <div>
      <Header />
      <Footer />
    </div>
  );
}
```

This works, but it adds an extra `<div>` to the DOM.

A Fragment groups the elements **without creating an additional DOM element**.

This is useful when the extra wrapper would be unnecessary or could interfere with:

* CSS layout
* Flexbox/Grid structure
* Semantic HTML
* DOM structure

---

## 7. JSX Self-Closing Tags

React allows components without children to use self-closing syntax.

Instead of:

```jsx
<Header></Header>
```

we can write:

```jsx
<Header />
```

These are equivalent when the component does not contain children.

Similarly:

```jsx
<img src="/image.png" alt="Example" />
```

HTML-style elements that do not contain children should also be properly self-closed in JSX.

---

## 8. Important React Concepts Learned Today

### Core Concepts

* React applications are built using **components**.
* Components are reusable pieces of UI.
* JSX allows HTML-like markup to be written inside JavaScript.
* `.jsx` files commonly contain JavaScript with JSX syntax.
* A component's returned JSX must have a single root.
* React Fragments can group multiple elements without adding an extra DOM element.
* `<>...</>` is shorthand for `<React.Fragment>...</React.Fragment>`.
* React components are normally named using **PascalCase**.
* Vite provides the development environment and build tooling for the React project.
* `npm install` installs project dependencies.
* `npm run dev` starts the development server.
* `package.json` defines project metadata, dependencies, and npm scripts.
* `package-lock.json` locks the resolved dependency versions.
* `node_modules` contains installed dependencies and should normally not be committed.
* `.gitignore` prevents specified files and directories from being tracked by Git.

---

## 9. Mental Model

A useful mental model for today's concepts:

```text
Browser
   │
   ▼
index.html
   │
   ▼
<div id="root">
   │
   ▼
main.jsx
   │
   ▼
<App />
   │
   ├── <Header />
   ├── <MainContent />
   │      ├── <Card />
   │      └── <Card />
   │
   └── <Footer />
```

The important idea is that a React application is essentially a **tree of components**.

As the application becomes larger, we break the UI into smaller components and compose them together.

---

## Key Takeaways

> **React → Components → JSX → Component Tree → UI**

The most important concepts from Day 01 are:

1. **Vite** is used to scaffold and run the React development environment.
2. **Components** are the fundamental building blocks of React applications.
3. **JSX** allows us to describe UI using HTML-like syntax inside JavaScript.
4. **Fragments** allow multiple JSX elements to be grouped without adding an extra DOM element.
5. **`main.jsx`** is the entry point that mounts the React application.
6. **`App.jsx`** commonly represents the root component.
7. **`package.json`** manages project metadata, scripts, and dependencies.
8. **`node_modules`** contains installed dependencies.
9. **`.gitignore`** prevents specified files from being tracked by Git.
10. A React application can be understood as a **tree of reusable components**.

---
### What I Learned

* How to create a React project using Vite.
* Basic React project structure.
* The purpose of important configuration and project files.
* What React components are.
* The basics of JSX.
* The purpose of `.jsx` files.
* Why React Fragments are needed.
* The difference between normal component tags and self-closing component syntax.
